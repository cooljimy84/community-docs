

## Operating System

OpenVoiceOS ready to use images come in several flavours;
The buildroot version, being the minimal consumer type of image and the Manjaro version, being the full distribution easy / easier for developing.

a headless raspbian image is also maintained by the community

### OpenVoiceOS

|                                                | ovos-buildroot                     | ovos-arch                 | ovos-raspbian                   |
|------------------------------------------------|------------------------------------|---------------------------|---------------------------------|
| **Operating System**                           |                                    |                           |                                 |
| Base OS                                        | buildroot                          | manjaro                   | raspbian                        |
| Last Updated - YYYY/MM/DD                      | 2023-0?-??                         | 2023-0?-??                | 2023-0?-??                      |
| **Customization**                              |                                    |                           |                                 |
| Open Build System                              | Yes                                | Yes                       | Yes<br>(pi-gen github workflow) |
| Package manager                                | N/A<br>(*No buildtools available*) | pacman                    | apt                             |
| **Software - Architecture**                    |                                    |                           |                                 |
| Core                                           | ovos-core                          | ovos-core                 | ovos-core                       |
| GUI                                            | ovos-shell                         | ovos-shell                | N/A                             |
| Launcher                                       | systemd<br>user session            | systemd<br>system session | systemd<br>user session         |
| **Updating**                                   |                                    |                           |                                 |
| Update mechanism                               | pip<br>(bash scripts)              | pip<br>(bash scripts)     | pip<br>(bash scripts)           |
| **Screen - GUI**                               |                                    |                           |                                 |
| GUI supported<br>*Show GUI if screen attached* | eglfs                              | eglfs                     | N/A                             |


### Friends

|                                                | NeonAI                    | Bigscreen                              |
|------------------------------------------------|---------------------------|----------------------------------------|
| **Operating System**                           |                           |                                        |
| Base OS                                        | debian                    | manjaro                                |
| Last Updated - YYYY/MM/DD                      | 2023-03 (regular updates) | [Rolling Release](https://github.com/manjaro-arm/bigscreen/releases)          |
| **Customization**                              |                           |                                        |
| Open Build System                              | Yes                       | [Manjaro ARM Tools](https://gitlab.manjaro.org/manjaro-arm/applications/manjaro-arm-tools)                               |
| Package manager                                | apt                       | pacman                                 |
| **Software - Architecture**                    |                           |                                        |
| Core                                           | neon-core                 | ovos-core                              |
| GUI                                            | ovos-shell                | Plasma Shell                           |
| Launcher                                       | systemd<br>system session | systemd<br>user session                |
| **Updating**                                   |                           |                                        |
| Update mechanism                               | PHAL plugin<br>(pip/git)  | package manager<br>(mycroft-bigscreen) |
| **Screen - GUI**                               |                           |                                        |
| GUI supported<br>*Show GUI if screen attached* | eglfs                     | X11/Wayland                            |


### Mycroft

|                                                | Mark 1<br>(Classic Core) | Mark 2<br>(Dinkum)                         | Picroft<br>(Classic Core) |
|------------------------------------------------|--------------------------|--------------------------------------------|---------------------------|
| **Operating System**                           |                          |                                            |                           |
| Base OS                                        | raspbian                 | Pantacor                                   | raspbian                  |
| Last Updated - YYYY/MM/DD                      | 20??-??-??               | 2023-??-??                                 | 20??-??-??                |
| **Customization**                              |                          |                                            |                           |
| Open Build System                              | github readme            | No (?)<br>*build tools are not public*     | github readme             |
| Package manager                                | apt                      | apt<br>(*limited by read-only filesystem*) | apt                       |
| **Software - Architecture**                    |                          |                                            |                           |
| Core                                           | mycroft-core             | dinkum                                     | mycroft-core              |
| GUI                                            | N/A                      | plasma-nano                                | N/A                       |
| Launcher                                       | systemd (?)              | Pantacor                                   | bash script               |
| **Updating**                                   |                          |                                            |                           |
| Update mechanism                               | package manager (?)      | OTA<br>*controlled by Mycroft*             | git pull                  |
| **Screen - GUI**                               |                          |                                            |                           |
| GUI supported<br>*Show GUI if screen attached* | N/A                      | X11                                        | N/A                       |


## Plugins

### OpenVoiceOS

|                         | ovos-buildroot                                    | ovos-arch                                         | ovos-raspbian                                     |
|-------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|
| **Default Plugins**     |                                                   |                                                   |                                                   |
| stt                     | ovos-stt-plugin-server<br>(ovos proxy)            | ovos-stt-plugin-server<br>(ovos proxy)            | ovos-stt-plugin-server<br>(ovos proxy)            |
| fallback_stt            | N/A                                               | N/A                                               | N/A                                               |
| tts                     | ovos-tts-plugin-mimic3-server<br>(public servers) | ovos-tts-plugin-mimic3-server<br>(public servers) | ovos-tts-plugin-mimic3-server<br>(public servers) |
| fallback_tts            | ovos-tts-plugin-mimic                             | ovos-tts-plugin-mimic                             | ovos-tts-plugin-mimic                             |
| **Recommended Plugins** |                                                   |                                                   |                                                   |
| STT - On device         | ovos-stt-plugin-vosk                              | ovos-stt-plugin-vosk                              | ovos-stt-plugin-vosk                              |
| STT - On premises       | ovos-stt-plugin-server<br>(any plugin)            | ovos-stt-plugin-server<br>(any plugin)            | ovos-stt-plugin-server<br>(any plugin)            |
| STT - Cloud             | ovos-stt-plugin-server<br>(ovos proxy)            | ovos-stt-plugin-server<br>(ovos proxy)            | ovos-stt-plugin-server<br>(ovos proxy)            |
| TTS - On device         | ovos-tts-plugin-mimic3                            | ovos-tts-plugin-mimic3                            | ovos-tts-plugin-mimic3                            |
| TTS - On premises       | ovos-tts-plugin-server<br>(any plugin)            | ovos-tts-plugin-server<br>(any plugin)            | ovos-tts-plugin-server<br>(any plugin)            |
| TTS - Cloud             | ovos-tts-plugin-mimic3-server<br>(public servers) | ovos-tts-plugin-mimic3-server<br>(public servers) | ovos-tts-plugin-mimic3-server<br>(public servers) |

### Friends

|                         	| NeonAI                                 | Bigscreen              	|
|-------------------------	|----------------------------------------|------------------------	|
| **Default Plugins**     	|                           	         |                        	|
| stt                     	| neon-stt-plugin-google-cloud-streaming | ovos-stt-plugin-server<br>(ovos proxy) |
| fallback_stt            	| ovos-stt-plugin-vosk      	         | N/A                      |
| tts                     	| neon-tts-plugin-coqui-remote           | ovos-tts-plugin-mimic2   |
| fallback_tts            	| neon-tts-plugin-coqui     	         | ovos-tts-plugin-mimic  	|
| **Recommended Plugins** 	|                           	         |                        	|
| STT - On device         	| ovos-stt-plugin-vosk                   | ovos-stt-plugin-vosk     |
| STT - On premises       	| neon-stt-plugin-nemo                   | ovos-stt-plugin-server<br>(any plugin) |
| STT - Cloud             	| neon-stt-plugin-google-cloud-streaming | ovos-stt-plugin-server<br>(ovos proxy) |
| TTS - On device         	| neon-tts-plugin-coqui                  | ovos-tts-plugin-mimic3   |
| TTS - On premises       	| neon-tts-plugin-coqui                  | ovos-tts-plugin-server<br>(any plugin) |
| TTS - Cloud             	| neon-tts-plugin-coqui     	         | ovos-tts-plugin-mimic3-server<br>(public servers) |

## Mycroft

|                         | Mark 1<br>(Classic Core)              | Mark 2<br>(Dinkum)                    | Picroft<br>(Classic Core)             |
|-------------------------|---------------------------------------|---------------------------------------|---------------------------------------|
| **Default Plugins**     |                                       |                                       |                                       |
| stt                     | mycroft (selene)<br>(internal plugin) | mycroft (selene)<br>(internal plugin) | mycroft (selene)<br>(internal plugin) |
| fallback_stt            | N/A<br>(missing feature)              | N/A<br>(missing feature)              | N/A<br>(missing feature)              |
| tts                     | mimic2<br>(internal plugin)           | mimic 3<br>(internal plugin)          | mimic2<br>(internal plugin)           |
| fallback_tts            | mimic<br>(internal plugin)            | mimic<br>(internal plugin)            | mimic<br>(internal plugin)            |
| **Recommended Plugins** |                                       |                                       |                                       |
| STT - On device         | N/A                                   | grokotron<br>(internal plugin)        | N/A                                   |
| STT - On premises       | N/A (?)                               | N/A                                   | N/A (?)                               |
| STT - Cloud             | mycroft (selene)<br>(internal plugin) | mycroft (selene)<br>(internal plugin) | mycroft (selene)<br>(internal plugin) |
| TTS - On device         | mimic<br>(internal plugin)            | mimic 3<br>(internal plugin)          | mimic<br>(internal plugin)            |
| TTS - On premises       | N/A (?)                               | N/A (?)                               | N/A (?)                               |
| TTS - Cloud             | mimic2<br>(internal plugin)           | N/A (?)                               | mimic2<br>(internal plugin)           |

## ???

### OpenVoiceOS

### Friends

## Mycroft