```bash
cp ~/Library/Caches/arduino/sketches/F711A1F952B387BC548683AB6FCDBEF3/weather.ino.bootloader.bin ./
cp ~/Library/Arduino15/packages/esp32/hardware/esp32/3.2.0/tools/partitions/boot_app0.bin ./  
cp ~/Library/Caches/arduino/sketches/F711A1F952B387BC548683AB6FCDBEF3/weather.ino.partitions.bin ./
cp ~/Library/Caches/arduino/sketches/F711A1F952B387BC548683AB6FCDBEF3/weather.ino.bin ./  
 
~/Library/Arduino15/packages/esp32/tools/esptool_py/4.9.dev3/esptool --chip esp32 merge_bin \
  -o aura-firmware.bin \
  --flash_mode dio \
  --flash_freq 40m \
  --flash_size 4MB \
  0x1000 weather.ino.bootloader.bin \
  0x8000 weather.ino.partitions.bin \
  0xe000 boot_app0.bin \
  0x10000 weather.ino.bin
  
~/Library/Arduino15/packages/esp32/tools/esptool_py/4.9.dev3/esptool --chip esp32 merge_bin \
  -o aura-firmware-inverted.bin \
  --flash_mode dio \
  --flash_freq 40m \
  --flash_size 4MB \
  0x1000 weather.ino.bootloader.bin \
  0x8000 weather.ino.partitions.bin \
  0xe000 boot_app0.bin \
  0x10000 weather.ino.bin
```
