<!--
date: '2010-08-24'
published: true
slug: 2010-08-android-web-gallery-example
time_to_read: 5
title: Android Web Gallery Example
-->

I’ve been dabbling since last Friday with Android development. So far, I’ve already released [one app](http://market.android.com/details?id=za.co.mtn) on the marketplace because its pretty straight-forward to get something done on the Android platform.  
  
My next challenge was to implement a picture gallery app and I found the following example:  
  
<http://www.androidpeople.com/android-gallery-imageview-example/>  
  
Also found an example of how to fetch images from the Web:  
  
<http://www.androidpeople.com/android-load-image-from-url-example/>  
  
So, all I needed to do was merge the two together…  
  
main.xml  
> <?xml version="1.0" encoding="utf-8"?>  
> <LinearLayout android:id="@+id/LinearLayout01"  
> android:layout\_width="fill\_parent" android:layout\_height="fill\_parent"  
> xmlns:android="<http://schemas.android.com/apk/res/android">  
> android:orientation="vertical">  
> <Gallery xmlns:android="<http://schemas.android.com/apk/res/android">  
> android:id="@+id/gallery"  
> android:layout\_width="fill\_parent"  
> android:layout\_height="wrap\_content"  
> />  
> <ImageView android:id="@+id/ImageView01"  
> android:layout\_width="wrap\_content"  
> android:layout\_height="wrap\_content"  
> />  
> </LinearLayout>

  
webGalleryExample.java  
> package za.co.mtn.webGalleryExample;  
>   
> import java.io.InputStream;  
> import java.net.URL;  
>   
> import android.app.Activity;  
> import android.content.Context;  
> import android.content.res.TypedArray;  
> import android.graphics.drawable.Drawable;  
> import android.os.Bundle;  
> import android.view.View;  
> import android.view.ViewGroup;  
> import android.widget.AdapterView;  
> import android.widget.BaseAdapter;  
> import android.widget.Gallery;  
> import android.widget.ImageView;  
> import android.widget.AdapterView.OnItemClickListener;  
>   
> public class GalleryExample extends Activity {  
> private String[] jamCamURLs = {  
> “<http://path.to.image1.jpg>”,  
> “<http://path.to.image2.jpg>”,  
> “<http://path.to.image3.jpg>”,  
>   
> };  
> Drawable[] drawablesFromUrl = new Drawable[3];  
> /\*\* Called when the activity is first created. \*/  
> @Override  
> public void onCreate(Bundle savedInstanceState) {  
> super.onCreate(savedInstanceState);  
> setContentView(R.layout.main);  
> for (int i = 0; i < drawablesFromUrl.length; i++){  
> drawablesFromUrl[i] = LoadImageFromURL(jamCamURLs[i]);  
> }  
> final ImageView imgView = (ImageView)findViewById(R.id.ImageView01);  
> imgView.setImageDrawable(drawablesFromUrl[0]);  
> Gallery g = (Gallery) findViewById(R.id.gallery);  
> g.setAdapter(new ImageAdapter(this));  
>   
> g.setOnItemClickListener(new OnItemClickListener() {  
> public void onItemClick(AdapterView parent, View v, int position, long id) {  
> imgView.setImageDrawable(drawablesFromUrl[position]);  
> }  
> });  
> }  
> private Drawable LoadImageFromURL(String url)  
> {  
> try  
> {  
> InputStream is = (InputStream) new URL(url).getContent();  
> Drawable d = Drawable.createFromStream(is, "src name");  
> return d;  
> }catch (Exception e) {  
> System.out.println("Exc="+e);  
> return null;  
> }  
> }  
> /\*public static boolean StoreByteImage(Context mContext, byte[] imageData,  
> int quality, String expName) {  
>   
> File sdImageMainDirectory = new File("/sdcard/myImages");  
> FileOutputStream fileOutputStream = null;  
> String nameFile = null;  
> try {  
>   
> BitmapFactory.Options options=new BitmapFactory.Options();  
> options.inSampleSize = 5;  
> Bitmap myImage = BitmapFactory.decodeByteArray(imageData, 0,  
> imageData.length,options);  
>   
> fileOutputStream = new FileOutputStream(  
> sdImageMainDirectory.toString() +"/" + nameFile + ".jpg");  
> BufferedOutputStream bos = new BufferedOutputStream(  
> fileOutputStream);  
>   
> myImage.compress(CompressFormat.JPEG, quality, bos);  
>   
> bos.flush();  
> bos.close();  
>   
> } catch (FileNotFoundException e) {  
> // TODO Auto-generated catch block  
> e.printStackTrace();  
> } catch (IOException e) {  
> // TODO Auto-generated catch block  
> e.printStackTrace();  
> }  
>   
> return true;  
> }\*/  
>   
> public class ImageAdapter extends BaseAdapter {  
> int mGalleryItemBackground;  
> private Context mContext;  
>   
> public ImageAdapter(Context c) {  
> mContext = c;  
> TypedArray a = obtainStyledAttributes(R.styleable.JamCam);  
> mGalleryItemBackground = a.getResourceId(  
> R.styleable.JamCam\_android\_galleryItemBackground, 0);  
> a.recycle();  
> }  
>   
> public int getCount() {  
> return jamCamURLs.length;  
> //return mImageIds.length;  
> }  
>   
> public Object getItem(int position) {  
> return position;  
> }  
>   
> public long getItemId(int position) {  
> return position;  
> }  
>   
> public View getView(int position, View convertView, ViewGroup parent) {  
> ImageView i = new ImageView(mContext);  
>   
> i.setImageDrawable(drawablesFromUrl[position]);  
> i.setLayoutParams(new Gallery.LayoutParams(70, 57));  
> i.setScaleType(ImageView.ScaleType.FIT\_XY);  
> i.setBackgroundResource(mGalleryItemBackground);  
>   
> return i;  
> }  
> }  
> }

  
And voila!  
  
  



## 5 comments captured from [original post](https://ysfk.blogspot.com/2010/08/android-web-gallery-example.html) on Blogger

**Bilder aus dem Internet in Grid View anzeigen - Android-Hilfe.de said on 2010-09-03**

[...]  [...]

**Yusuf said on 2010-09-03**

That is all of it, what do you think is missing?

**ron said on 2010-11-01**

Hi, i tried your code and run on 2.0 emulator but getting &quot;The application WebGallery (process za.co.mtn.webGalleryExample) has stopped unexpectedly. Pleasetry again.&quot; Did you encounter this? Thanks

**Yusuf said on 2010-11-01**

Hello, have you set the permissions for your app? (It requires permissions to be set for accessing the Internet).

**Yusuf said on 2010-12-30**

Hello, R refers to resource and JamCam is the name that I gave to the app I was developing. Change JamCam to the name of your main class?



[Original post](https://ysfk.blogspot.com/2010/08/android-web-gallery-example.html)

#howto #legacy-blogger 