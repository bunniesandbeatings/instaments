# Beat Step Pro MCU Mode Control Analysis

## Pattern 1,3,5,7 etc .. 15
  * **PORT:** 2 (BSP Editor In/Out)
  * **CHANNEL:** Always channel 1

1. Key Press `90 08 7F`
    1. Note x08 is Pad 1, x09 is Pad 3, etc.
    2. Full velocity
3. Indicate:
    1. ON
    ```
    90 73 7F  # display? 
    90 08 7F  # expect this to set the key?
    ```
    1. OFF:
    ```
    90 73 00 
    90 08 00
    ```
1. Key Release `90 08 00`


## Pattern 2,3,6,8 etc .. 16
Almost the same except:

1. `90 73 7F` this `73` pattern is not returned to the BSP
2. Note x10 is pad 2, x11 for pad 3


1. Key Press `90 08 7F`
    1. Note 8 is Pad 1, 9 is Pad 3, etc.
    2. Full velocity
3. Indicate:
    ```
    90 73 7F  # display?
    90 08 7F  # expect this to set the key?
    ```
1. Key Release `90 08 00`
        


# Beat Step Pro MCU Mode Control Captures
## Patern Control
### Ptn 1 (on blue)

```
22:38:24.961	From BeatStepPro OutEditor  	Note On	1	90 08 7F
0	To BeatStepProInEditor	Note On	1	90 73 7F
0	To BeatStepProInEditor	Note On	1	90 08 7F
22:38:25.021	From BeatStepPro OutEditor  	Note On	1	90 08 00

```

### Ptn 3 (switch from 1 - turns 1 off)

```
22:41:05.044	From BeatStepPro OutEditor  	Note On	1	90 09 7F
0	To BeatStepProInEditor	Note On	1	90 73 7F
0	To BeatStepProInEditor	Note On	1	90 09 7F
0	To BeatStepProInEditor	Note On	1	90 73 7F
0	To BeatStepProInEditor	Note On	1	90 08 00
22:41:05.131	From BeatStepPro OutEditor  	Note On	1	90 09 00
```

### Ptn 2 (on red)

```
22:39:22.476	From BeatStepPro OutEditor  	Note On	1	90 10 7F
0	To BeatStepProInEditor	Note On	1	90 10 7F
22:39:22.545	From BeatStepPro OutEditor  	Note On	1	90 10 00

```

### Ptn 2 (off red)

```
22:40:06.442	From BeatStepPro OutEditor  	Note On	1	90 10 7F
0	To BeatStepProInEditor	Note On	1	90 10 00
22:40:06.541	From BeatStepPro OutEditor  	Note On	1	90 10 00
```

### Ptn 4 (on red - to see the note assignment)
```
22:42:30.963	From BeatStepPro OutEditor  	Note On	1	90 11 7F
0	To BeatStepProInEditor	Note On	1	90 11 7F
22:42:31.021	From BeatStepPro OutEditor  	Note On	1	90 11 00
```

### Rotary 1 (Pan from C to l1 back to r2)
```
22:45:05.923	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:05.941	To BeatStepProInEditor	Control	1	B0 30 16
22:45:05.967	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.066	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 34 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:06.104	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.148	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 33 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:06.190	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.227	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.277	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 32 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:06.336	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.398	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.479	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 31 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:06.616	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.680	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 43 20 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:06.815	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.857	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 31 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:06.892	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:06.996	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 32 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:07.168	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 31 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:07.718	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:07.743	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:07.763	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 32 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:07.789	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:07.811	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:07.865	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 34 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:08.010	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:08.114	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:08.171	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:08.217	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:08.240	To BeatStepProInEditor	Control	1	B0 30 15
22:45:08.251	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 35 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:08.303	From BeatStepPro OutEditor  	Control	1	B0 10 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:08.384	From BeatStepPro OutEditor  	Control	1	B0 10 41
22:45:09.251	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.275	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.307	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.337	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.355	To BeatStepProInEditor	Control	1	B0 30 16
22:45:09.375	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 35 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:09.401	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.441	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.476	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 34 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:09.516	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.559	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 32 4C 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:09.603	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.641	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.670	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.690	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.714	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.744	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 43 20 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:09.798	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.845	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:09.883	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 31 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:09.910	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 32 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:09.984	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:10.029	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:10.135	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:10.172	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 33 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:10.208	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:10.242	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 34 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:10.298	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:10.333	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:10.370	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 35 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:45:10.388	To BeatStepProInEditor	Control	1	B0 30 17
22:45:10.396	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:10.508	From BeatStepPro OutEditor  	Control	1	B0 10 01
22:45:10.535	From BeatStepPro OutEditor  	Control	1	B0 10 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 20 37 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
```

### Rotary 2 (for data comparison)
```
22:46:42.972	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.004	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.033	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.071	From BeatStepPro OutEditor  	Control	1	B0 11 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 20 39 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:43.118	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.152	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.176	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.201	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.232	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.253	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.274	From BeatStepPro OutEditor  	Control	1	B0 11 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 31 31 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:43.295	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.316	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.335	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.373	From BeatStepPro OutEditor  	Control	1	B0 11 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 31 32 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:43.420	From BeatStepPro OutEditor  	Control	1	B0 11 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 31 33 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:43.483	From BeatStepPro OutEditor  	Control	1	B0 11 41
22:46:43.524	From BeatStepPro OutEditor  	Control	1	B0 11 41
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 31 34 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:43.639	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.681	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.702	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.727	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.751	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.781	From BeatStepPro OutEditor  	Control	1	B0 11 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 31 32 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:43.804	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.829	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.861	From BeatStepPro OutEditor  	Control	1	B0 11 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 31 30 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:43.893	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.925	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:43.965	From BeatStepPro OutEditor  	Control	1	B0 11 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 20 39 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:43.997	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:44.036	From BeatStepPro OutEditor  	Control	1	B0 11 01
22:46:44.059	From BeatStepPro OutEditor  	Control	1	B0 11 01
0	To BeatStepProInEditor	SysEx		F0 00 00 66 14 12 38 20 20 36 52 20 20 20 20 20 38 4C 20 20 20 20 20 32 52 20 20 20 20 20 43 20…
22:46:44.100	From BeatStepPro OutEditor  	Control	1	B0 11 01
```

### Rotary 9 (vol)

```
22:47:13.655	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 6B
22:47:13.678	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 6A
22:47:13.703	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 69
22:47:13.727	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 68
22:47:13.792	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 67
22:47:13.854	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 66
22:47:13.901	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 65
22:47:13.934	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 64
22:47:13.969	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 63
22:47:13.997	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 62
22:47:14.032	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 61
22:47:14.068	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 60
22:47:14.122	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5F
22:47:14.173	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5E
22:47:14.242	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5D
22:47:14.279	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5C
22:47:14.316	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5B
22:47:14.343	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5A
22:47:14.364	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 59
22:47:14.385	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 58
22:47:14.600	To BeatStepProInEditor	Pitch Wheel	1	E0 67 58
22:47:14.673	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 57
22:47:14.775	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 58
22:47:14.870	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 59
22:47:14.928	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5A
22:47:14.950	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5B
22:47:14.979	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5C
22:47:15.004	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5D
22:47:15.027	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5E
22:47:15.047	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 5F
22:47:15.073	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 60
22:47:15.102	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 61
22:47:15.130	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 62
22:47:15.150	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 63
22:47:15.170	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 64
22:47:15.209	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 65
22:47:15.255	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 66
22:47:15.298	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 67
22:47:15.317	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 68
22:47:15.344	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 69
22:47:15.368	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 6A
22:47:15.407	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 6B
22:47:15.438	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 6C
22:47:15.477	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 6D
22:47:15.513	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 6E
22:47:15.726	To BeatStepProInEditor	Pitch Wheel	1	E0 67 6E
22:47:17.055	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 6F
22:47:17.117	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 70
22:47:17.198	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 71
22:47:17.247	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 72
22:47:17.282	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 73
22:47:17.316	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 74
22:47:17.351	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 75
22:47:17.373	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 76
22:47:17.403	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 77
22:47:17.433	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 78
22:47:17.482	From BeatStepPro OutEditor  	Pitch Wheel	1	E0 67 79
22:47:17.700	To BeatStepProInEditor	Pitch Wheel	1	E0 67 79
```

### Rotary 10 for comparison

```
22:47:38.691	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 68
22:47:38.712	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 67
22:47:38.733	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 66
22:47:38.752	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 62
22:47:38.773	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 61
22:47:38.792	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 60
22:47:38.813	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5F
22:47:38.834	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5E
22:47:38.855	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5D
22:47:38.898	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5C
22:47:38.934	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5B
22:47:38.979	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5A
22:47:39.021	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 59
22:47:39.083	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 58
22:47:39.131	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 57
22:47:39.309	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 58
22:47:39.367	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 59
22:47:39.388	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5A
22:47:39.409	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5B
22:47:39.430	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 5F
22:47:39.449	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 60
22:47:39.470	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 61
22:47:39.491	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 62
22:47:39.512	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 63
22:47:39.545	From BeatStepPro OutEditor  	Pitch Wheel	2	E1 67 64
22:47:39.760	To BeatStepProInEditor	Pitch Wheel	2	E1 67 64
```
