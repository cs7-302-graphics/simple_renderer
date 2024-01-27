# Introduction to Computer Graphics (CS7.302, IIIT Hyderabad)

This is the base code that is to be used for all assignments in the above course. <br>
Some sample scenes are given in the <a href="https://github.com/cs7-302-graphics/scenes">cs7-302-graphics/scenes</a> repo.

<br><br>
Instructions to clone, compile and run are given below.

## Cloning this repo
```git clone --recursive https://github.com/cs7-302-graphics/code```
Do not forget the ```--recursive``` flag!

## Compiling
```
mkdir build
cd build
cmake ..
```

If you are on windows, this should create a Visual Studio solution ```cs7302.sln``` in the build folder. Open it and compile. \
If you are on linux/mac, you will need to additionally run the following to compile:

```
make -j8
```

## Specifying the Scene config file
The path to scene config (typically names ```config.json```) is specified in the ```main()``` function in ```render.cpp```. Similarly, the path where the rendered image is saved is also specified here.
```
int main()
{
    Scene scene("C:\\Users\\Aakash\\Desktop\\2024_COMPUTER_GRAPHICS_COURSE\\scenes\\cornell_box\\config.json");

    Integrator rayTracer(scene);
    auto renderTime = rayTracer.render();

    std::cout << "Render Time: " << std::to_string(renderTime / 1000.f) << " ms" << std::endl;
    rayTracer.outputImage.save("C:\\Users\\Aakash\\Desktop\\temp.png");

    return 0;
}
```
