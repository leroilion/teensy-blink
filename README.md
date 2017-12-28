# Blink example

## Tools

### Meson

Need to install [meson build](http://mesonbuild.com/)

```
sudo apt install meson
```

### Ninja
Need to install [ninja build](https://ninja-build.org/)

```
sudo apt install ninja-build
```

### Teensy_loader_cli
Clone and compile [teensy_loader_cli](https://github.com/PaulStoffregen/teensy_loader_cli)

```
sudo apt install libusb-dev # Need libusb-dev to compile teensy loader cli
cd /opt
git clone https://github.com/PaulStoffregen/teensy_loader_cli.git
cd teensy_loader_cli
make
```

## Subprojects

Clone teensy-core for meson

```
mkdir subprojects
git clone git@github.com:leroilion/teensy-core.git subprojects/teensy-core
cd subprojects/teensy-core
git checkout -b v1.35
cd -
```

## Compile

```
meson build --cross-file subprojects/teensy-core/teensy-3.5-cross.txt
cd build
ninja
```
