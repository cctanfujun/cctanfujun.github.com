---
layout: 	post
title: 	RecyclerView缓存和onBindViewHolder的第三个参数
subtitle: 	"recyclerview的一点点优化"
date:       2016-12-14
author:     "晓晨DEV"
header-img: "img/post-bg-default4.png"
tags:
 - Android
 - Java

---


RecyclerView 有三级缓存（也有说成四级的）其中二级缓存是开发者设定的 ViewCacheExtension 缓存帮助类。

背景：我们有一个列表，列表每个item都有一个下载按钮，下载的应用状态变化，对于条目的按钮也应该发生变化，而且为了效率需要局部刷新。

问题出现：为了列表流畅设置了 setItemViewCacheSize 然后当某个 ViewItem 出现在界面上的时候 onBindViewHolder 没有回调，导致按钮状态不正确。

目前我们局部刷新的做法是，bindView 的时候给 item 的 view 设置 tag，当下载状态改变的时候，从可视的view中去找到对应的 item ，再找到需要改变的按钮，去变化它。但是如果 onBindViewHolder 没有回调，tag 也设置的不正确，就没法找到这个View更新这个按钮了。

这时候有些小伙伴要说了，recyclerview 的 adapter 有 notifyitemchanged（int pos）方法的，收到回调的时候去更新这个 item 就行了啊，但是因为我们图片加载是在 onBindViewHolder 中去做的,这样会造成 item 闪烁，所以后来换成了
上面描述的方式。新的问题是在 setItemViewCacheSize 为一个偏大数的时候被引入了，因为这个 itemviewCache 默认的值是2,不设置这个的话，问题不是那么容易被发现。

解决问题：难道 google 没有考虑到我们局部刷新的诉求吗？并不是这样的，
recyclerView 的 adapter 有一个这样的方法，但是它不是抽象的，可能很多小伙伴没有注意到。

```Java
public void onBindViewHolder(VHholder, int position, List<Object> payloads) {
            onBindViewHolder(holder, position);
        }
```
调用 `public final void notifyItemChanged(int position, Object payload)` 可以把数据传到三参数回调中，这样就可以进行局部刷新，而不会发生闪烁。

```Java
@Override
    public void onBindViewHolder(ViewHolderholder, int position, List<Object> payloads) {
        if (payloads.isEmpty()) {
            // payloads 为 空，说明是更新整个 ViewHolder
            onBindViewHolder(holder, position);
        } else {
            // payloads 不为空，这只更新需要更新的 View 即可。
            holder.mBadgeView.setVisibility(((Item)payloads.get(0)).disabled ? View.VISIBLE : View.INVISIBLE);
        }
    }

```
payloads不会为null，只可能为空。

接下来就是从list中找到pos了,我们这里需要遍历下数据集，不过我觉得这块是我们下载内部的设计问题了，之后再考虑。