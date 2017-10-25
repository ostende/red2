	[with_libxine=$withval],[with_libxine=no])
if test "$with_libxine" = "yes"; then
	PKG_CHECK_MODULES(LIBXINE, libxine)
	AC_DEFINE([WITH_XINE],[1],[Define to 1 if you have libxine])
fi
AM_CONDITIONAL(HAVE_LIBXINE, test "$with_libxine" = "yes")

AC_ARG_WITH(debug,
	AS_HELP_STRING([--without-debug],[disable debugging code]),
	[with_debug="$withval"],[with_debug="yes"])
if test "$with_debug" = "yes"; then
	AC_DEFINE([DEBUG],[1],[Define to 1 to enable debugging code])
fi

AC_ARG_WITH(memcheck,
	AS_HELP_STRING([--with-memcheck],[enable memory leak checks]),
	[with_memcheck="$withval"],[with_memcheck="no"])
if test "$with_memcheck" = "yes"; then
	AC_DEFINE([MEMLEAK_CHECK],[1],[Define to 1 to enable memory leak checks])
fi

AC_ARG_WITH(fbdev,
	AC_HELP_STRING([--with-fbdev=devicename], [use devicename for framebuffer device, e.g. /dev/fb0 ]),
	[[with_fbdev=$withval]],
	[[with_fbdev=no]]
)
if test x"$with_fbdev" != xno ; then
	AC_DEFINE_UNQUOTED(FB_DEV, "$withval", [Defines which device to use for main framebuffer (e.g. /dev/fb0)])
fi

AC_ARG_WITH(lcddev,
	AC_HELP_STRING([--with-lcddev=devicename], [use devicename for lcd framebuffer device, e.g. /dev/fb1 ]),
	[[with_lcddev=$withval]],
	[[with_lcddev=no]]
)
if test x"$with_lcddev" != xno ; then
	AC_DEFINE_UNQUOTED(LCD_DEV, "$withval", [Defines which device to use for lcd (e.g. /dev/fb1)])
fi

ENIGMA2_CFLAGS="-fno-rtti -fno-exceptions -rdynamic -funwind-tables"
AC_SUBST(ENIGMA2_CFLAGS)

CPPFLAGS="$CPPFLAGS $PYTHON_CPPFLAGS"
CFLAGS="$CFLAGS -Wall"
CXXFLAGS="$CXXFLAGS -Wall $BASE_CFLAGS $ENIGMA2_CFLAGS $PTHREAD_CFLAGS $OPENMP_CFLAGS $ALSA_CFLAGS $GLES_CFLAGS"
AX_SWIG_PYTHON_OPT="$AX_SWIG_PYTHON_OPT -DSWIG_PYTHON_LEGACY_BOOL"

AC_CONFIG_FILES([
Makefile
data/Makefile
data/fonts/Makefile
data/piconlcd/Makefile
data/countries/Makefile
data/defaults/Makefile
data/defaults/Dream/Makefile
data/defaults/Dream/hdbouquets/Makefile
data/defaults/Dream/sdbouquets/Makefile
data/extensions/Makefile
data/keymaps/Makefile
data/skin_default/Makefile
data/skin_default/buttons/Makefile
data/skin_default/spinner/Makefile
include/Makefile
lib/Makefile
lib/base/Makefile
lib/python/Makefile
lib/python/Components/Makefile
lib/python/Components/Converter/Makefile
lib/python/Components/Renderer/Makefile
lib/python/Components/Sources/Makefile
lib/python/Screens/Makefile
lib/python/Plugins/Makefile
lib/python/Plugins/DemoPlugins/Makefile
lib/python/Plugins/DemoPlugins/TPMDemo/Makefile
lib/python/Plugins/DemoPlugins/TestPlugin/Makefile
lib/python/Plugins/Extensions/BhEpgBackup/Makefile
lib/python/Plugins/Extensions/BhFastEpg/Makefile
lib/python/Plugins/Extensions/BhFullBackup/Makefile
lib/python/Plugins/Extensions/BhPersonalBackup/Makefile
lib/python/Plugins/Extensions/BhPersonalBackup/icons/Makefile
lib/python/Plugins/Extensions/BhWeather/Makefile
lib/python/Plugins/Extensions/CutListEditor/Makefile
lib/python/Plugins/Extensions/CutListEditor/meta/Makefile
lib/python/Plugins/Extensions/DVDBurn/Makefile
lib/python/Plugins/Extensions/DVDBurn/meta/Makefile
lib/python/Plugins/Extensions/DVDPlayer/Makefile
lib/python/Plugins/Extensions/DVDPlayer/meta/Makefile
lib/python/Plugins/Extensions/DVDPlayer/src/Makefile
lib/python/Plugins/Extensions/GraphMultiEPG/Makefile
lib/python/Plugins/Extensions/GraphMultiEPG/meta/Makefile
lib/python/Plugins/Extensions/Makefile
lib/python/Plugins/Extensions/MediaPlayer/Makefile
lib/python/Plugins/Extensions/MediaPlayer/meta/Makefile
lib/python/Plugins/Extensions/MediaScanner/Makefile
lib/python/Plugins/Extensions/MediaScanner/meta/Makefile
lib/python/Plugins/Extensions/Modem/Makefile
lib/python/Plugins/Extensions/PicturePlayer/Makefile
lib/python/Plugins/Extensions/PicturePlayer/meta/Makefile
lib/python/Plugins/Extensions/PicturePlayer/data/Makefile
lib/python/Plugins/Extensions/SocketMMI/Makefile
lib/python/Plugins/Extensions/SocketMMI/meta/Makefile
lib/python/Plugins/Extensions/SocketMMI/src/Makefile
lib/python/Plugins/Extensions/TuxboxPlugins/Makefile
lib/python/Plugins/Extensions/TuxboxPlugins/meta/Makefile
lib/python/Plugins/Extensions/WebBrowser/Makefile
lib/python/Plugins/Extensions/WebBrowser/meta/Makefile
lib/python/Plugins/Extensions/WebBrowser/keymap/Makefile
lib/python/Plugins/Extensions/WebBrowser/desc/Makefile
lib/python/Plugins/Extensions/StreamTV/Makefile
lib/python/Plugins/Extensions/StreamTV/meta/Makefile
lib/python/Plugins/Extensions/StreamTV/icons/Makefile
lib/python/Plugins/Extensions/DLNAServer/Makefile
lib/python/Plugins/Extensions/DLNAServer/meta/Makefile
lib/python/Plugins/Extensions/DLNABrowser/Makefile
lib/python/Plugins/Extensions/DLNABrowser/meta/Makefile
lib/python/Plugins/Extensions/HbbTV/Makefile
lib/python/Plugins/Extensions/HbbTV/meta/Makefile
lib/python/Plugins/Extensions/HbbTV/locale/Makefile
lib/python/Plugins/SystemPlugins/BlackHoleApi/Makefile
lib/python/Plugins/Extensions/SatipClient/Makefile
lib/python/Plugins/Extensions/SatipClient/meta/Makefile
lib/python/Plugins/Extensions/MiniTV/Makefile
lib/python/Plugins/Extensions/MiniTV/meta/Makefile
lib/python/Plugins/SystemPlugins/CleanupWizard/Makefile
lib/python/Plugins/SystemPlugins/CleanupWizard/meta/Makefile
lib/python/Plugins/SystemPlugins/CommonInterfaceAssignment/Makefile
lib/python/Plugins/SystemPlugins/CommonInterfaceAssignment/meta/Makefile
lib/python/Plugins/SystemPlugins/CrashlogAutoSubmit/Makefile
lib/python/Plugins/SystemPlugins/CrashlogAutoSubmit/meta/Makefile
lib/python/Plugins/SystemPlugins/DefaultServicesScanner/Makefile
lib/python/Plugins/SystemPlugins/DefaultServicesScanner/meta/Makefile
lib/python/Plugins/SystemPlugins/DiseqcTester/Makefile
lib/python/Plugins/SystemPlugins/DiseqcTester/meta/Makefile
lib/python/Plugins/SystemPlugins/FrontprocessorUpgrade/Makefile
lib/python/Plugins/SystemPlugins/FrontprocessorUpgrade/meta/Makefile
lib/python/Plugins/SystemPlugins/Hotplug/Makefile
lib/python/Plugins/SystemPlugins/Hotplug/meta/Makefile
lib/python/Plugins/SystemPlugins/Makefile
lib/python/Plugins/SystemPlugins/TempFanControl/Makefile
lib/python/Plugins/SystemPlugins/TempFanControl/meta/Makefile
lib/python/Plugins/SystemPlugins/NetworkWizard/Makefile
lib/python/Plugins/SystemPlugins/NetworkWizard/meta/Makefile
lib/python/Plugins/SystemPlugins/NFIFlash/Makefile
lib/python/Plugins/SystemPlugins/NFIFlash/meta/Makefile
lib/python/Plugins/SystemPlugins/PositionerSetup/Makefile
lib/python/Plugins/SystemPlugins/PositionerSetup/meta/Makefile
lib/python/Plugins/SystemPlugins/SatelliteEquipmentControl/Makefile
lib/python/Plugins/SystemPlugins/SatelliteEquipmentControl/meta/Makefile
lib/python/Plugins/SystemPlugins/Satfinder/Makefile
lib/python/Plugins/SystemPlugins/Satfinder/meta/Makefile
lib/python/Plugins/SystemPlugins/SkinSelector/Makefile
lib/python/Plugins/SystemPlugins/SkinSelector/meta/Makefile
lib/python/Plugins/SystemPlugins/SoftwareManager/Makefile
lib/python/Plugins/SystemPlugins/SoftwareManager/meta/Makefile
lib/python/Plugins/SystemPlugins/VideoEnhancement/Makefile
lib/python/Plugins/SystemPlugins/VideoEnhancement/meta/Makefile
lib/python/Plugins/SystemPlugins/VideoTune/Makefile
lib/python/Plugins/SystemPlugins/VideoTune/meta/Makefile
lib/python/Plugins/SystemPlugins/Videomode/Makefile
lib/python/Plugins/SystemPlugins/Videomode/meta/Makefile
lib/python/Plugins/SystemPlugins/WirelessLan/Makefile
lib/python/Plugins/SystemPlugins/WirelessLan/meta/Makefile
lib/python/Plugins/SystemPlugins/Fancontrol/Makefile
lib/python/Plugins/SystemPlugins/Fancontrol/meta/Makefile
lib/python/Plugins/SystemPlugins/FPGAUpgrade/Makefile
lib/python/Plugins/SystemPlugins/FPGAUpgrade/meta/Makefile
lib/python/Plugins/SystemPlugins/WirelessLanSetup/Makefile
lib/python/Plugins/SystemPlugins/WirelessLanSetup/meta/Makefile
lib/python/Plugins/SystemPlugins/ManualFancontrol/Makefile
lib/python/Plugins/SystemPlugins/ManualFancontrol/meta/Makefile
lib/python/Plugins/SystemPlugins/Blindscan/Makefile
lib/python/Plugins/SystemPlugins/Blindscan/meta/Makefile
lib/python/Plugins/SystemPlugins/RemoteControlCode/Makefile
lib/python/Plugins/SystemPlugins/RemoteControlCode/meta/Makefile
lib/python/Plugins/SystemPlugins/UI3DSetup/Makefile
lib/python/Plugins/SystemPlugins/UI3DSetup/meta/Makefile
lib/python/Plugins/SystemPlugins/UIPositionSetup/Makefile
lib/python/Plugins/SystemPlugins/UIPositionSetup/meta/Makefile
lib/python/Plugins/SystemPlugins/HDMICEC/Makefile
lib/python/Plugins/SystemPlugins/HDMICEC/components/Makefile
lib/python/Plugins/SystemPlugins/HDMICEC/meta/Makefile
lib/python/Plugins/SystemPlugins/LEDBrightnessSetup/Makefile
lib/python/Plugins/SystemPlugins/LEDBrightnessSetup/meta/Makefile
lib/python/Plugins/SystemPlugins/FirmwareUpgrade/Makefile
lib/python/Plugins/SystemPlugins/FirmwareUpgrade/meta/Makefile
lib/python/Plugins/SystemPlugins/CrashReport/Makefile
lib/python/Plugins/SystemPlugins/CrashReport/meta/Makefile
lib/python/Plugins/SystemPlugins/3GModemManager/Makefile
lib/python/Plugins/SystemPlugins/3GModemManager/meta/Makefile
lib/python/Plugins/SystemPlugins/3GModemManager/script/Makefile
lib/python/Plugins/SystemPlugins/WirelessAccessPoint/Makefile
lib/python/Plugins/SystemPlugins/WirelessAccessPoint/meta/Makefile
lib/python/Plugins/SystemPlugins/ZappingModeSelection/Makefile
lib/python/Plugins/SystemPlugins/ZappingModeSelection/meta/Makefile
lib/python/Plugins/SystemPlugins/DeviceManager/Makefile
lib/python/Plugins/SystemPlugins/DeviceManager/meta/Makefile
lib/python/Plugins/SystemPlugins/DeviceManager/locale/Makefile
lib/python/Plugins/SystemPlugins/TransCodingSetup/Makefile
lib/python/Plugins/SystemPlugins/TransCodingSetup/meta/Makefile
lib/python/Plugins/SystemPlugins/TransCodingSetup/locale/Makefile
lib/python/Plugins/SystemPlugins/WOLSetup/Makefile
lib/python/Plugins/SystemPlugins/WOLSetup/meta/Makefile
lib/python/Plugins/SystemPlugins/NetDrive/Makefile
lib/python/Plugins/SystemPlugins/NetDrive/meta/Makefile
lib/python/Plugins/SystemPlugins/AudioEffect/Makefile
lib/python/Plugins/SystemPlugins/AudioEffect/meta/Makefile
lib/python/Plugins/SystemPlugins/AnimationSetup/Makefile
lib/python/Plugins/SystemPlugins/AnimationSetup/meta/Makefile
lib/python/Plugins/SystemPlugins/BoxModeConfig/Makefile
lib/python/Plugins/SystemPlugins/BoxModeConfig/meta/Makefile
lib/python/Plugins/SystemPlugins/Solo4kMiscControl/Makefile
lib/python/Plugins/SystemPlugins/Solo4kMiscControl/meta/Makefile
lib/python/Plugins/SystemPlugins/FastChannelChange/Makefile
lib/python/Plugins/SystemPlugins/FastChannelChange/meta/Makefile
lib/python/Plugins/SystemPlugins/Ultimo4kMiscControl/Makefile
lib/python/Plugins/SystemPlugins/Ultimo4kMiscControl/meta/Makefile
lib/python/Blackhole/Makefile
lib/python/Tools/Makefile
po/Makefile
main/Makefile
tools/Makefile
tools/enigma2.sh
enigma2.pc
])
AC_OUTPUT

