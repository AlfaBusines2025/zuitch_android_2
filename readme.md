cd C:\Users\mateo\AppData\Local\Android\Sdk\platform-tools

:: 1) Limpia el buffer
adb -s 1152725455005754 logcat -c
adb -s emulator-5554 logcat -c

:: 2) Obtén el PID de tu app
for /f %i in ('adb -s emulator-5554 shell pidof com.zuitch.app') do set APP_PID=%i

:: 3) Muestra SOLO las últimas N líneas y sale (no queda en streaming)
adb -s emulator-5554 logcat --pid=%APP_PID% -v threadtime -t 100

adb logcat
