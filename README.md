# proj_launch

## Overview
This package manages scripts that collectively launch in-vehicle software managed by this organization.

## Node Graph
![node graph](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/eve-autonomy/proj_launch/docs/node_graph.pu)

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

