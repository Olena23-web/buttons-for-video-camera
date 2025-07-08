# buttons-for-video-camera
cmds:
  # The order corresponds to the customer's specified parameters
  CAM_POWER:
    active: true
    path: System
    Name: Power
    Command:
      packet: 8x 01 04 00 0p FF
    InquiryCommand:
      packet: 8x 09 04 00 FF
      reply: y0 50 0p FF
    Value:
      Type: reference
      ReferenceKey: ONOFF
  CAM_ZOOM_STOP:
    active: true
    Path: Zoom
    Name: Zoom Stop
    ShortName: Stop
    Command:
      Type: OneShot
      packet: 8x 01 04 07 00 FF
  CAM_ZOOM_TELE_STEP:
    active: true
    Path: Zoom
    Name: Zoom Tele Step
    ShortName: Tele Step
    Command:
      Type: OneShot
      packet: 8x 01 04 07 02 FF
  CAM_ZOOM_WIDE_STEP:
    active: true
    Path: Zoom
    Name: Zoom Wide Step
    ShortName: Wide Step
    Command:
      Type: OneShot
      packet: 8x 01 04 07 03 FF
  CAM_ZOOM_SPEED:
    active: true
    id: 12
    Path: Zoom
    Name: Zoom Speed
    Short: Zoom
    Command:
      Type: Speed
      packet: 8x 01 04 07 00 FF
      inc_packet: 8x 01 04 07 2p FF
      dec_packet: 8x 01 04 07 3p FF
    Value:
      Type: int
      Range:
        min: 0
        max: 7
  CAM_ZOOM_DIRECT:
    active: true
    path: PTZ/Position
    Name: Absolute Zoom Position
    ShortName: AbsZoomPos
    Command:
      packet: 8x 01 04 47 0p 0p 0p 0p FF
    Value:
      Type: int
      Range:
        min: 0
        max: 0x4000
        fineSteps: 1
        coarseSteps: 100
  CAM_ZOOM_DIRECT_WITH_SPEED:
    active: true
    path: PTZ/Position
    Name: Absolute Zoom Position with speed
    ShortName: AbsZoomPosSpeed
    Command:
      packet: 8x 0A 04 47 0t 0p 0q 0r 0s FF
    Value:
      Type: int
      Range:
        min: 0
        max: 0x4000
        fineSteps: 1
        coarseSteps: 100
