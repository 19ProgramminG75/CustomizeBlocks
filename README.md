# Components and Blocks
-----
# blocks

## Status bar

For activity screen use `getWindow()`
For fragments screen use `getActivity()`

```java
{
  getWindow().getDecorView().setSystemUiVisibility( View.SYSTEM_UI_FLAG_LAYOUT_STABLE | View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN | View.SYSTEM_UI_FLAG_HIDE_NAVIGATION | View.SYSTEM_UI_FLAG_LAYOUT_HIDE_NAVIGATION | View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY ); 
}
```
You can use `TRANSPARENT` or `Opacity` [8-digit Hexadecimal](https://davidwalsh.name/hex-opacity)
```java
{
  getWindow().setStatusBarColor(Color.TRANSPARENT);
}
```
To support android 11+
```java
{
  getWindow().setFlags(WindowManager.LayoutParams.FLAG_DRAWS_SYSTEM_BAR_BACKGROUNDS, WindowManager.LayoutParams.FLAG_DRAWS_SYSTEM_BAR_BACKGROUNDS); 
}

```
### Final Code
```java
{
  getWindow().getDecorView().setSystemUiVisibility( View.SYSTEM_UI_FLAG_LAYOUT_STABLE | View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN | View.SYSTEM_UI_FLAG_HIDE_NAVIGATION | View.SYSTEM_UI_FLAG_LAYOUT_HIDE_NAVIGATION | View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY ); 
}
{
  getWindow().setStatusBarColor(Color.TRANSPARENT); 
}
{
  getWindow().setFlags(WindowManager.LayoutParams.FLAG_DRAWS_SYSTEM_BAR_BACKGROUNDS, WindowManager.LayoutParams.FLAG_DRAWS_SYSTEM_BAR_BACKGROUNDS); 
}
```

## Screen Customization

```java
DisplayMetrics displayMetrics = new DisplayMetrics();

// to get the windows density
getWindowManager().getDefaultDisplay().getMetrics(displayMetrics);

//to get the fragment density
//int density = getActivity().getResources().getDisplayMetrics().densityDpi;

//get the screen width
int width_px = Resources.getSystem().getDisplayMetrics().widthPixels;

//get the screen height 
int height_px =Resources.getSystem().getDisplayMetrics().heightPixels;

//get the pixel DIP (Dots Per Inch)
int pixeldpi = Resources.getSystem().getDisplayMetrics().densityDpi;

//get the status bar height
//sbh stands for statusBarHeight
double sbh = Math.ceil(25 * Resources.getSystem().getDisplayMetrics().density);

//get the value of ( screen width by pixels / pixels density ) * 160
int width_dp = (width_px/pixeldpi)*160;

int height_dp = (height_px/pixeldpi)*160;
linear3.setTranslationY((float)(-(height_px)));
//int total = sbh + sbh;
//linear1 contains imageview
linear1.setLayoutParams(new LinearLayout.LayoutParams((int) width_px,(int) height_px));
//linear2 contains textview button iamges more on factionalities
linear2.setLayoutParams(new LinearLayout.LayoutParams((int) width_px,(int) height_px - sbh));
((LinearLayout.LayoutParams) linear3.getLayoutParams()).setMargins(0 , (int)sbh, 0, 0);
//marginToAdd = ((int)(Resources.getSystem().getDisplayMetrics().density * sbh));
//linear3.setMargins((int)sbh, (int)sbh, (int)sbh, (int)sbh);
```

[DisplayMetrics displayMetrics = new DisplayMetrics();](https://stackoverflow.com/a/45257847/19917623) origin storkoverflow

[double statusBarHeight = Math.ceil(25 * Resources.getSystem().getDisplayMetrics().density);](https://stackoverflow.com/a/7643649/19917623) origin stockoverflow

[Pixel = DP * (DPI/160)](https://www.pixelconverter.com/dp-to-pixel-converter/) origin pixelconverter

## Examples

To achive that output you need to use [Status Bar](https://github.com/19ProgramminG75/CustomizeBlocks/blob/main/README.md#status-bar)
and use this screen scaling to get the perfect output [Screen](https://github.com/19ProgramminG75/CustomizeBlocks/edit/main/README.md#screen-customization)
## Example1

| linear1     | linear2      | output     |
| ------------- | ------------- | -------- |
| ![linear2](https://github.com/19ProgramminG75/CustomizeBlocks/blob/58bbbf3025eed636c2d54d8e354a53bc96db0b91/app/src/main/res/drawable/HD-Player_1efIVHaL6g.png?raw=true)          | ![linear2](https://github.com/19ProgramminG75/CustomizeBlocks/blob/4639de590ef6a8c9fff734646de417e0c4b89a7e/app/src/main/res/drawable/HD-Player_9owIo7fyWW.png?raw=true)         | ![ouutput](https://github.com/19ProgramminG75/CustomizeBlocks/blob/4639de590ef6a8c9fff734646de417e0c4b89a7e/app/src/main/res/drawable/HD-Player_v7NMBcBWHI.png?raw=true)  |
-----
## Example2
| linear1     | linear2      | output     |
| ------------- | ------------- | -------- |
| ![linear1](https://github.com/19ProgramminG75/CustomizeBlocks/blob/399f39aacf644a6bc98efeac95eb2eaa947fb831/app/src/main/res/drawable/HD-Player_n7lP7sgl7U.png?raw=true)          | ![linear2](https://github.com/19ProgramminG75/CustomizeBlocks/blob/main/app/src/main/res/drawable/HD-Player_aSNwEswaBW.png?raw=true)         | ![ouutput](https://github.com/19ProgramminG75/CustomizeBlocks/blob/399f39aacf644a6bc98efeac95eb2eaa947fb831/app/src/main/res/drawable/HD-Player_FpDXC6fTDz.png?raw=true)  |
