
## Comand base per connettersi

wget http://xxxx:xxxxx@http://192.xx.xx.xx/web/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=focusin


Video & Snapshot

    VLC Stream (High Resolution)
        rtsp://admin:instar@IP-Address:554/11

    VLC Stream (High Resolution)
        rtsp://admin:instar@IP-Address:RTSP-Port/11
    VLC Stream (Medium Resolution)
        rtsp://admin:instar@IP-Address:RTSP-Port/12
    VLC Stream (Low Resolution)
        rtsp://admin:instar@IP-Address:RTSP-Port/13
    Snapshot (720p)
        http://IP-Address:Port/tmpfs/snap.jpg?usr=admin&pwd=instar
    Snapshot (352p)
        http://IP-Address:Port/tmpfs/auto.jpg?usr=admin&pwd=instar
    Snapshot (176p)
        http://IP-Address:Port/tmpfs/auto2.jpg?usr=admin&pwd=instar
    MJPEG Stream 11
        http://IP-Address:Port/mjpegstream.cgi?-chn=11&-usr=admin&-pwd=instar
    MJPEG Stream 12
        http://IP-Address:Port/mjpegstream.cgi?-chn=12&-usr=admin&-pwd=instar
    MJPEG Stream 13
        http://IP-Address:Port/mjpegstream.cgi?-chn=13&-usr=admin&-pwd=instar

Also note the additional SDK documentation for accessing video / audio
Pan & Tilt

    Moves continuously right
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=right
    Moves continuously left
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=left
    Moves continuously up
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=up
    Moves continuously down
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=down
    Stops moving camera-head
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=stop
    Moves one step right
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=1&-act=right
    Moves one step left
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=1&-act=left
    Moves one step up
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=1&-act=up
    Moves one step down
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=1&-act=down
    Go to Center Position
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=home
    Scan horizontal
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=hscan
    Scan vertical
        http://IP-Address:Port/cgi-bin/hi3510/ptzctrl.cgi?-step=0&-act=vscan
    Set a position
        http://IP-Address:Port/cgi-bin/hi3510/preset.cgi?-act=set&-status=1&-number=[0-7]
    Unset a position
        http://IP-Address:Port/cgi-bin/hi3510/preset.cgi?-act=set&-status=0&-number=[0-7]
    goto to a set position
        http://IP-Address:Port/cgi-bin/hi3510/preset.cgi?-act=goto&-status=1&-number=[0-7]

Image

    Sets the Image Parameter
        http://IP-Address:Port/cgi-bin/hi3510/param.cgi?cmd=setimageattr

You can set the following parameters:

    brightness :: [0 - 255] the bigger the value the brighter the image
    saturation :: [0 - 255] the bigger the value the more saturation the image has
    contrast :: [0 - 255] the bigger the value the more contrast the image has
    hue :: [0 - 127] the bigger the value the more hue the image has
    flip :: [on , off] flips the image
    mirror :: [on , off] flips the image
    scene :: [auto , indoor , outdoor] sets the white balance mode

Example:

    WLAN
        http://IP-Address:Port/cgi-bin/hi3510/param.cgi?cmd=setimageattr&-brightness=0&-saturation=0&-contrast=0&-hue=0&-flip=off&-mirror=off&-scene=auto
    Reset the Parameter Values
        http://IP-Address:Port/cgi-bin/hi3510/param.cgi?cmd=setwirelessattr

Example:

    IR-LED
        http://IP-Address:Port/cgi-bin/hi3510/param.cgi?cmd=setwirelessattr&-wf_ssid=SSID&-wf_enable=0&-wf_auth=2&-wf_key=1234&-wf_enc=1&-wf_mode=0
    Sets IR LED's to auto mode
        http://192.168.178.87/cgi-bin/hi3510/param.cgi?cmd=setinfrared&-infraredstat=auto
    Sets IR LED's always active :: only IN-6011
        http://192.168.178.87/cgi-bin/hi3510/param.cgi?cmd=setinfrared&-infraredstat=open
    Sets IR LED's always inactive
        http://192.168.178.87/cgi-bin/hi3510/param.cgi?cmd=setinfrared&-infraredstat=close

Alarm

    trigger an alarm on your camera
        http://admin:instar@192.168.xxx.xxx/cgi-bin/hi3510/param.cgi?cmd=pushhostalarm
    enables the md area 1
        http://admin:instar@192.168.xxx.xxx/cgi-bin/hi3510/param.cgi?cmd=setmdattr&-enable=1&-name=1
    disables the md area 1
        http://admin:instar@192.168.xxx.xxx/cgi-bin/hi3510/param.cgi?cmd=setmdattr&-enable=0&-name=1
    enable / disable external alarm in to trigger recording
        http://192.168.x.x/cgi-bin/hi3510/param.cgi?cmd=setioattr&-io_enable=1&-io_flag=1

Example:

    Camera Model
        http://admin:instar@192.168.xxx.xxx/cgi-bin/hi3510/param.cgi?cmd=setmdattr&-enable=0&-name=1&cmd=setmdattr&-enable=0&-name=2&cmd=setmdattr&-enable=0&-name=3&cmd=setmdattr&-enable=0&-name=4

Installing the wrong Firmware can overwrite your camera Identification. Use the following commands to reset your camera model:

    Set your Camera Model
        http://192.168.178.133:83/param.cgi?cmd=get_instar_guest&-index=47

    Get set camera model
        http://192.168.178.133:83/param.cgi?cmd=set_instar_guest&-index=47&-value=6014

    Set PoE or WiFi Model:
        http://192.168.178.133:83/param.cgi?cmd=get_instar_guest&-index=48

    Get PoE variable :: PoE (true) or WLAN (false)
        http://192.168.178.133:83//param.cgi?cmd=set_instar_guest&-index=48&-value=false
