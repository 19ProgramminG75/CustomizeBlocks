## Components and Blocks
-----
### blocks

#### screen




| linear1     | linear2      | output     |
| ------------- | ------------- | -------- |
| ![linear2](https://github.com/19ProgramminG75/CustomizeBlocks/blob/main/app/src/main/res/drawable/HD-Player_FgEhlBiUFz.png?raw=true)          | ![linear2](https://github.com/19ProgramminG75/CustomizeBlocks/blob/main/app/src/main/res/drawable/HD-Player_FgEhlBiUFz.png?raw=true)         | ![linear2](https://github.com/19ProgramminG75/CustomizeBlocks/blob/main/app/src/main/res/drawable/HD-Player_FgEhlBiUFz.png?raw=true)  |

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
double statusBarHeight = Math.ceil(25 * Resources.getSystem().getDisplayMetrics().density);

int sbh = (int) statusBarHeight;
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

-----

