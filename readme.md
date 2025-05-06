# UBICACION DE ACD

- C:\Users\mateo\AppData\Local\Android\Sdk\build-tools

# Limpia de logs

adb.exe logcat -c

# Terminal

for /f %i in ('adb.exe shell pidof com.zuitch.app') do adb.exe logcat --pid=%i -v threadtime

cd "C:\Users\mateo\AppData\Local\Android\Sdk\platform-tools"
adb logcat -c
for /f "tokens=2" %i in ('adb shell ps ^| findstr com.zuitch.app') do adb logcat --pid=%i -v threadtime
