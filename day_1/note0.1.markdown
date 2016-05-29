#day_01 部分布局文件


##head.xml:

```


<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#EF7011" >

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="50dp"
        android:gravity="center_horizontal"
        android:orientation="vertical"
        android:padding="5dp" >

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="@drawable/d1" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="2dp"
            android:gravity="center"
            android:text="1°C ~ 13°C"
            android:textColor="@android:color/white"
            android:textSize="10sp" />
    </LinearLayout>

    <ImageView
        android:id="@+id/iv_title"
        android:layout_width="wrap_content"
        android:layout_height="50dp"
        android:layout_centerHorizontal="true"
        android:src="@drawable/navigation_title" />

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="50dp"
        android:layout_toRightOf="@+id/iv_title"
        android:src="@drawable/navigation_refresh" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="50dp"
        android:layout_toLeftOf="@+id/iv_credit"
        android:gravity="center"
        android:text="115"
        android:textColor="@android:color/white"
        android:textSize="16sp" />

    <ImageView
        android:id="@+id/iv_credit"
        android:layout_width="wrap_content"
        android:layout_height="50dp"
        android:layout_alignParentRight="true"
        android:layout_alignParentTop="true"
        android:padding="5dp"
        android:src="@drawable/navigation_credit_icon" />

</RelativeLayout>



```



##bottom.xml

```

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal" >

    <LinearLayout
        android:id="@+id/id_lv_bottom_news"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center_horizontal"
        android:orientation="vertical" >

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="@drawable/tab_icon_news_light" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:paddingBottom="2dp"
            android:paddingTop="2dp"
            android:text="新闻"
            android:textColor="#EF7011" />
    </LinearLayout>

    <LinearLayout
        android:id="@+id/id_lv_bottom_friends"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center_horizontal"
        android:orientation="vertical" >

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/selector_friends" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:paddingBottom="2dp"
            android:paddingTop="2dp"
            android:text="并友" />
    </LinearLayout>

    <LinearLayout
        android:id="@+id/id_lv_bottom_money"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center_horizontal"
        android:orientation="vertical" >

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="@drawable/selector_money" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:paddingBottom="2dp"
            android:paddingTop="2dp"
            android:text="抢钱" />
    </LinearLayout>

    <LinearLayout
        android:id="@+id/id_lv_bottom_me"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center_horizontal"
        android:orientation="vertical" >

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/selector_me" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:paddingBottom="2dp"
            android:paddingTop="2dp"
            android:text="我 " />
    </LinearLayout>

</LinearLayout>

```


##activity_main.xml

```
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context="com.fushui.news_day01.MainActivity" >

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true" >

        <include layout="@layout/headview" />
    </LinearLayout>


    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true" >

        <include layout="@layout/bottomview" />
    </LinearLayout>

</RelativeLayout>

```


##去除标题栏的两种方法

1. 在代码中实现：


在此方法setContentView（R.layout.main）之前加入：
requestWindowFeature(Window.FEATURE_NO_TITLE);标题栏就没有了。

2. 在AndroidManifest.xml中实现：
注册Activity时加上如下的一句配置就可以实现。


```
<activity  android:name=".Activity"
       android:theme="@android:style/Theme.NoTitleBar"
  ></activity>

```
