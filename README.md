# proj_launch

## Overview
This package manages scripts that collectively launch in-vehicle software managed by this organization.

## Node Graph
![node graph](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/eve-autonomy/proj_launch/docs/node_graph.pu)

<details><summary>List of repositories</summary><div>

- Nodes
  - System State management:
    - [/autoware_state_machine](https://github.com/eve-autonomy/autoware_state_machine)
  - HMI control:
    - Sound control:
      - [/ad_sound_manager](https://github.com/eve-autonomy/ad_sound_manager)
      - /sound_bgm[/audio_driver](https://github.com/eve-autonomy/audio_driver)
      - /sound_voice_alarm[/audio_driver](https://github.com/eve-autonomy/audio_driver)
    - Lamp control:
      - [/ad_status_lamp_manager](https://github.com/eve-autonomy/ad_status_lamp_manager)
      - [/delivery_reservation_lamp_manager](https://github.com/eve-autonomy/delivery_reservation_lamp_manager)
      - [/warning_lamp_manager](https://github.com/eve-autonomy/warning_lamp_manager)
    - Button control:
      - [/button_manager](https://github.com/eve-autonomy/button_manager)
      - [/engage_srv_converter](https://github.com/eve-autonomy/engage_srv_converter)
  - Delivery reservation app cooperation:
    - [/go_interface](https://github.com/eve-autonomy/go_interface)
  - V2I infrastructure cooperation:
    - [/v2i_interface](https://github.com/eve-autonomy/v2i_interface)

- Message definition
  - System State management:
    - [autoware_state_machine_msgs](https://github.com/eve-autonomy/autoware_state_machine_msgs)
  - HMI control:
    - Sound control:
      - [audio_driver_msgs](https://github.com/eve-autonomy/audio_driver_msgs)
  - Delivery reservation app cooperation:
    - [go_interface](https://github.com/eve-autonomy/go_interface)

- Parameters
  - Delivery reservation app cooperation:
    - [go_interface_params.default](https://github.com/eve-autonomy/go_interface_params.default)
  - V2I infrastructure cooperation:
    - [v2i_interface_params.default](https://github.com/eve-autonomy/v2i_interface_params.default)

- Dataset
  - HMI control:
    - Sound control:
      - [ad_sound.default](https://github.com/eve-autonomy/ad_sound.default)

</div></details>

## Environment variables

|Name|Description|
|:---|:----------|
|OPR_MODE_DELY_RSV|Select the operation mode of the delivery reservation apps from the following; `product`, `server_test`, `local_test`, `not_use`. This setting is reflected in the value of [`operation_mode`](https://github.com/eve-autonomy/go_interface#launch-arguments) in go_interface.|
|ACCESS_TOKEN_DELY_RSV|Specifies the access token of the delivery reservation apps. This setting is reflected in the value of [`access_token`](https://github.com/eve-autonomy/go_interface#launch-arguments) in go_interface.|
|AD_SOUND_LANGUAGE|Specifies the language of the audio file. This setting is reflected in the value of [`lang`](https://github.com/eve-autonomy/ad_sound_manager#launch-arguments) in ad_sound_manager.|

## Launch arguments

|Name|Description|
|:---|:----------|
|use_overridable_vehicle|Whether the vehicle can transfer driving authority by the operator's brakes.|
|operation_mode_v2i_infra|Select the operation mode of the v2i interface from the following; `product`, `local_test`. This setting is reflected in the value of [`operation_mode`](https://github.com/eve-autonomy/v2i_interface#launch-arguments) in v2i_interface.|
|operation_mode_delivery_reservation|It is basically the same as `OPR_MODE_DELY_RSV`[^1].|
|access_token_delivery_reservation|It is basically the same as `ACCESS_TOKEN_DELY_RSV`[^1].|
|ad_sound_language|It is basically the same as `AD_SOUND_LANGUAGE`[^1].|

[^1]: You can execute it by ignoring the environment variable setting by specifying an arbitrary value for this variable.

