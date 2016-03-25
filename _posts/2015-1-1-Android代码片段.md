---
layout: post
title: Android代码片段
excerpt: "Android代码片段"
tags: [Android]
categories: [Android]
modified: 2016-03-21
comments: true
---


# Android 代码片段

## 单例模式 

### 双重校检写法

```java

public class Singleton{
  private volatile static Singleton singleton;
  private Singleton(){}
  public static Singleton getSingleton(){
    if(singleton == null){
      synchronized (Singleton.class){
        if(singleton == null){
          singleton = new Singleton();
        }
      }
    }
  }

}



```

### 静态内部类写法

```java

public class Singleton { 
  private static class SingletonHolder {
  private static final Singleton INSTANCE = new Singleton(); 
  } 
  private Singleton (){} 
  public static final Singleton getInstance() { 
    return SingletonHolder.INSTANCE; 
  } 
}

```

## Drawable互转Bitmap

### Drawable转Bitmap

```java
Resources res = getResources();
Drawable drawable = res.getDrawable(R.drawable.myimage);
BitmapDrawable bd = (BitmapDrawable) d;
Bitmap bm = bd.getBitmap();
```

``` java
public static Bitmap drawableToBitmap(Drawable drawable) {       
        Bitmap bitmap = Bitmap.createBitmap(
              drawable.getIntrinsicWidth(),
              drawable.getIntrinsicHeight(),
              drawable.getOpacity()!=PixelFormat.OPAQUE ? Bitmap.Config.ARGB_8888:Bitmap.Config.RGB_565);
        Canvas canvas = new Canvas(bitmap);
        //canvas.setBitmap(bitmap);
        drawable.setBounds(0, 0,drawable.getIntrinsicWidth(),drawable.getIntrinsicHeight());
        drawable.draw(canvas);
        return bitmap;
}

```

### Bitmap转Drawable

``` java
Bitmap bm=xxx; //xxx根据你的情况获取
BitmapDrawable bd=BitmapDrawable(bm);
BtimapDrawable是Drawable的子类，最终直接使用bd对象即可。

mPicPath//本地图片路径转成Bitmap格式
Bitmap pic = BitmapFactory.decodeFile(this.mPicPath);
		image.setImageBitmap(pic);
转成Bitmap格式

```
## String与InputStream相互转换

### String to InputStream

```java
String str = "String与InputStream相互转换";
InputStream   in_nocode   =   new   ByteArrayInputStream(str.getBytes());   
InputStream   in_withcode   =   new   ByteArrayInputStream(str.getBytes("UTF-8"));
InputStream to String

```
### InputStream to String

方法1：
```java
public String convertStreamToString(InputStream is) {   
 BufferedReader reader = new BufferedReader(new InputStreamReader(is));   
      StringBuilder sb = new StringBuilder();   
  
      String line = null;   
      try {   
          while ((line = reader.readLine()) != null) {   
              sb.append(line + "/n");   
          }   
      } catch (IOException e) {   
          e.printStackTrace();   
      } finally {   
          try {   
              is.close();   
          } catch (IOException e) {   
              e.printStackTrace();   
          }   
      }   
  
      return sb.toString();   
  }
  
```  

方法2：

```java
public String inputStream2String (InputStream in) throws  IOException { 
        StringBuffer  out = new StringBuffer(); 
        byte[] b = new byte[4096]; 
        for (int n; (n = in.read(b)) != -1;){ 
            out.append(new String(b,0,n)); 
        } 
        return out.toString(); 
}

```
方法3：

```java
public static String inputStream2String(InputStream is) throws  IOException{ 
        ByteArrayOutputStream baos  = new ByteArrayOutputStream(); 
        int i=-1; 
        while((i=is.read())!=-1){ 
        baos.write(i); 
        } 
       return baos.toString(); 
}
```

## Bitmap 和 byte[]互转

### Bitmap → byte[]

```java
private byte[] Bitmap2Bytes(Bitmap bm){
    ByteArrayOutputStream baos = new ByteArrayOutputStream();
    bm.compress(Bitmap.CompressFormat.PNG, 100, baos);
    return baos.toByteArray();   
}


```
### byte[] → Bitmap

```java
private Bitmap Bytes2Bimap(byte[] b){
    if(b.length!=0){
        return BitmapFactory.decodeByteArray(b, 0, b.length);
    } else {
          return null;
           }
}

```

### 保存图片到sd卡

```java
public void saveBitmapToFile(String url, String filePath) {
        File iconFile = new File(filePath);
        if (!iconFile.getParentFile().exists()) {
            iconFile.getParentFile().mkdirs();
        }
 
        if (iconFile.exists() && iconFile.length() > 0) {
            return;
        }
 
        FileOutputStream fos = null;
        InputStream is = null;
        try {
            fos = new FileOutputStream(filePath);
            is = new URL(url).openStream();
 
            int data = is.read();
            while (data != -1) {
                fos.write(data);
                data = is.read();
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if (is != null) {
                    is.close();
                }
                if (fos != null) {
                    fos.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
    
```    
### 判断sd卡是否存在

```java
public boolean CheckSD() {
    if (android.os.Environment.getExternalStorageState().equals(
            android.os.Environment.MEDIA_MOUNTED)) {
        return true;
    } else {
        return false;
    }
}    
```       
## dip转px

```java
public int convertDipOrPx(int dip) {
    float scale = MarketApplication.getMarketApplicationContext()
            .getResources().getDisplayMetrics().density;
    return (int) (dip * scale + 0.5f * (dip >= 0 ? 1 : -1));
}       

```

## 网络

### 判断网络是否可用：

方法一：

```java

/**
     * 网络是否可用
     * 
     * @param context
     * @return
     */
    public static boolean isNetworkAvailable(Context context) {
        ConnectivityManager mgr = (ConnectivityManager) context.getSystemService(Context.CONNECTIVITY_SERVICE);
        NetworkInfo[] info = mgr.getAllNetworkInfo();
        if (info != null) {
            for (int i = 0; i < info.length; i++) {
                if (info[i].getState() == NetworkInfo.State.CONNECTED) {
                    return true;
                }
            }
        }
        return false;
    }
```    

方法二：

```java

/*
 * 判断网络连接是否已开 2012-08-20true 已打开 false 未打开
 */
public static boolean isConn(Context context) {
    boolean bisConnFlag = false;
    ConnectivityManager conManager = (ConnectivityManager) context
            .getSystemService(Context.CONNECTIVITY_SERVICE);
    NetworkInfo network = conManager.getActiveNetworkInfo();
    if (network != null) {
        bisConnFlag = conManager.getActiveNetworkInfo().isAvailable();
    }
     return bisConnFlag;
}

```

### 判断是不是Wifi连接

```java

public static boolean isWifiActive(Context icontext) {
    Context context = icontext.getApplicationContext();
    ConnectivityManager connectivity = (ConnectivityManager) context
            .getSystemService(Context.CONNECTIVITY_SERVICE);
    NetworkInfo[] info;
    if (connectivity != null) {
        info = connectivity.getAllNetworkInfo();
        if (info != null) {
            for (int i = 0; i < info.length; i++) {
                if (info[i].getTypeName().equals("WIFI")
                        && info[i].isConnected()) {
                    return true;
                }
            }
        }
    }
    return false;
}

```

### 判断当前网络类型

```java
private static int netCheck(Context context) {
        ConnectivityManager conMan = (ConnectivityManager) context
                .getSystemService(Context.CONNECTIVITY_SERVICE);
        State mobile = conMan.getNetworkInfo(ConnectivityManager.TYPE_MOBILE)
                .getState();
        State wifi = conMan.getNetworkInfo(ConnectivityManager.TYPE_WIFI)
                .getState();
        if (wifi.equals(State.CONNECTED)) {
            return DO_WIFI;
        } else if (mobile.equals(State.CONNECTED)) {
            return DO_3G;
        } else {
            return NO_CONNECTION;
        }
    }

```    

### 判断是否APK是否安装过

```java

public boolean checkApkExist(Context context, String packageName) {
        if (packageName == null || "".equals(packageName))
            return false;
        try {
            ApplicationInfo info = context.getPackageManager()
                    .getApplicationInfo(packageName,
                            PackageManager.GET_UNINSTALLED_PACKAGES);
            return true;
        } catch (NameNotFoundException e) {
            return false;
        } catch (NullPointerException e) {
            return false;
        }
    }
```    
### 安装APK


```java
public void installApk(Context context, String strFileAllName) {
    File file = new File(strFileAllName);
    Intent intent = new Intent();
    intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
    intent.setAction(Intent.ACTION_VIEW);
    String type = "application/vnd.android.package-archive";
    intent.setDataAndType(Uri.fromFile(file), type);
    context.startActivity(intent);
}
```
### 卸载APK

```java
public void UninstallApk(Context context, String strPackageName) {
    Uri packageURI = Uri.parse("package:" + strPackageName);
    Intent uninstallIntent = new Intent(Intent.ACTION_DELETE, packageURI);
    context.startActivity(uninstallIntent);
}
```