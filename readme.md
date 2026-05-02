I recently discovered GlowOGFN, 
a Fortnite OGFN. Since I like to cheat,
I decided to reverse their anticheat, 
and I saw something that shocked me. It checks by .exe and window name—basically, the strings aren't even obfuscated. the worst anticheat ever. 
That's why I'm sharing the complete bypass of the anti-cheat and IMGUI detection, etc.

I'm not sharing the source code because I'm giving the creator a month to contact me (@ntwritefile on discord ).

here some of their anticheat check... prepare your eyes...

```cpp
__int64 __fastcall sub_180009B10(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  const char *v5; // rdx
  // antidebug etc check..
  if ( (unsigned __int8)sub_180009170(a2) || (unsigned __int8)sub_1800095C0(a2) )
  {
    v4 = 16;
    v5 = "injector_process";
  }
  else
  {
    v4 = 18;
    v5 = "suspicious_process";
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  sub_18001F9B0(a1, v5, v4);
  return a1;
}
// sub_180009170 like bro wtf your checking with string... pls...
  {
    Init_thread_header(&dword_1800CBA40);
    if ( dword_1800CBA40 == -1 )
    {
      xmmword_1800CBA48 = 0;
      qword_1800CBA58 = 0;
      memset(v12, 0, sizeof(v12));
      sub_18001E900(v12, L"injector", 8);
      memset(v13, 0, sizeof(v13));
      sub_18001E900(v13, L"dll injector", 12);
      memset(v14, 0, sizeof(v14));
      sub_18001E900(v14, L"dllinjector", 11);
      memset(v15, 0, sizeof(v15));
      sub_18001E900(v15, L"jitbit", 6);
      memset(v16, 0, sizeof(v16));
      sub_18001E900(v16, L"manual map", 10);
      memset(v17, 0, sizeof(v17));
      sub_18001E900(v17, L"manualmap", 9);
      memset(v18, 0, sizeof(v18));
      sub_18001E900(v18, L"loadlibrary", 11);
      memset(v19, 0, sizeof(v19));
      sub_18001E900(v19, L"blackbone", 9);
      memset(v20, 0, sizeof(v20));
      sub_18001E900(v20, L"guidedhacking", 13);
      memset(v21, 0, sizeof(v21));
      sub_18001E900(v21, L"gh injector", 11);
      memset(v22, 0, sizeof(v22));
      sub_18001E900(v22, L"extreme injector", 16);
      memset(v23, 0, sizeof(v23));
      sub_18001E900(v23, L"x64 injector", 12);
      memset(v24, 0, sizeof(v24));
      sub_18001E900(v24, L"x64injector", 11);
      memset(v25, 0, sizeof(v25));
      sub_18001E900(v25, L"uuu client", 10);
      memset(v26, 0, sizeof(v26));
      sub_18001E900(v26, L"uuuclient", 9);
      memset(v27, 0, sizeof(v27));
      sub_18001E900(v27, L"xenos", 5);
      memset(v28, 0, sizeof(v28));
      sub_18001E900(v28, L"kiero", 5);
      memset(v29, 0, sizeof(v29));
      sub_18001E900(v29, L"minhook", 7);
      v11[0] = v12;
      v11[1] = &v30;
      sub_180008880(&xmmword_1800CBA48, v11);
      `eh vector destructor iterator'(v12, 0x20u, 0x12u, sub_18001EEB0);
      atexit(sub_18009C130);
      Init_thread_footer(&dword_1800CBA40);
    }
  }
// sub_1800095C0 brooooo...
 {
    Init_thread_header(&dword_1800CBA60);
    if ( dword_1800CBA60 == -1 )
    {
      xmmword_1800CBA68 = 0;
      qword_1800CBA78 = 0;
      memset(v12, 0, sizeof(v12));
      sub_18001E900(v12, L"cheat engine", 12);
      memset(v13, 0, sizeof(v13));
      sub_18001E900(v13, L"cheatengine", 11);
      memset(v14, 0, sizeof(v14));
      sub_18001E900(v14, L"process hacker", 14);
      memset(v15, 0, sizeof(v15));
      sub_18001E900(v15, L"processhacker", 13);
      memset(v16, 0, sizeof(v16));
      sub_18001E900(v16, L"x64dbg", 6);
      memset(v17, 0, sizeof(v17));
      sub_18001E900(v17, L"ollydbg", 7);
      memset(v18, 0, sizeof(v18));
      sub_18001E900(v18, L"interception", 12);
      v11[0] = v12;
      v11[1] = &v19;
      sub_180008880(&xmmword_1800CBA68, v11);
      `eh vector destructor iterator'(v12, 0x20u, 7u, sub_18001EEB0);
      atexit(sub_18009C140);
      Init_thread_footer(&dword_1800CBA60);
    }
  }
// NOOOO ANTICHEAT REPORT...
LODWORD(v103[15]) = 4;
  v6 = sub_180014FA0(v103, "{");
  v7 = sub_180014FA0(v6, "\"type\":\"anticheat_alert\",");
  v8 = sub_180014FA0(v7, "\"reason\":\"");
  v9 = (_QWORD *)sub_1800048A0(&Src);
  v10 = v9[2];
  if ( v9[3] > 0xFu )
    v9 = (_QWORD *)*v9;
  v11 = sub_18001BF40(v8, v9, v10);
  v12 = sub_180014FA0(v11, "\",");
  v13 = sub_180014FA0(v12, "\"suspect\":\"");
  v14 = (_QWORD *)sub_1800048A0(&v89);
  v15 = v14[2];
  if ( v14[3] > 0xFu )
    v14 = (_QWORD *)*v14;
  v16 = sub_18001BF40(v13, v14, v15);
  v17 = sub_180014FA0(v16, "\",");
  v18 = sub_180014FA0(v17, "\"details\":\"");
  v19 = (_QWORD *)sub_1800048A0(&v87);
  v20 = v19[2];
  if ( v19[3] > 0xFu )
    v19 = (_QWORD *)*v19;
  v21 = sub_18001BF40(v18, v19, v20);
  v22 = sub_180014FA0(v21, "\",");
  v23 = sub_180014FA0(v22, "\"username\":\"");
  v24 = (_QWORD *)sub_1800048A0(&v85);
  v25 = v24[2];
  if ( v24[3] > 0xFu )
    v24 = (_QWORD *)*v24;
  v26 = sub_18001BF40(v23, v24, v25);
  v27 = sub_180014FA0(v26, "\",");
  v28 = sub_180014FA0(v27, "\"accountId\":\"");
  v29 = (_QWORD *)sub_1800048A0(&v83);
  v30 = v29[2];
  if ( v29[3] > 0xFu )
    v29 = (_QWORD *)*v29;
  v31 = sub_18001BF40(v28, v29, v30);
  v32 = sub_180014FA0(v31, "\",");
  v33 = sub_180014FA0(v32, "\"email\":\"");
  v34 = (_QWORD *)sub_1800048A0(&v81);
  v35 = v34[2];
  if ( v34[3] > 0xFu )
    v34 = (_QWORD *)*v34;
  v36 = sub_18001BF40(v33, v34, v35);
  v37 = sub_180014FA0(v36, "\",");
  v38 = sub_180014FA0(v37, "\"encryptedIp\":\"");
  v39 = (_QWORD *)sub_1800048A0(&v79);
  v40 = v39[2];
  if ( v39[3] > 0xFu )
    v39 = (_QWORD *)*v39;
  v41 = sub_18001BF40(v38, v39, v40);
  v42 = sub_180014FA0(v41, "\",");
  v43 = sub_180014FA0(v42, "\"deviceFingerprint\":\"");
  v44 = (_QWORD *)sub_1800048A0(&v77);
  v45 = v44[2];
  if ( v44[3] > 0xFu )
    v44 = (_QWORD *)*v44;
  v46 = sub_18001BF40(v43, v44, v45);
  v47 = sub_180014FA0(v46, "\",");
  v48 = sub_180014FA0(v47, "\"hwid\":\"");
  v49 = (_QWORD *)sub_1800048A0(&Block);
  v50 = v49[2];
  if ( v49[3] > 0xFu )
    v49 = (_QWORD *)*v49;
  v51 = sub_18001BF40(v48, v49, v50);
  v52 = sub_180014FA0(v51, "\",");
  v53 = sub_180014FA0(v52, "\"processId\":");
  CurrentProcessId = GetCurrentProcessId();
  v55 = std::ostream::operator<<(v53, CurrentProcessId);
  v56 = sub_180014FA0(v55, ",");
  v57 = sub_180014FA0(v56, "\"timestamp\":");
  v58 = _time64(0);
  v59 = std::ostream::operator<<(v57, v58);
  sub_180014FA0(v59, "}");
  if ( v76.m128i_i64[1] > 0xFuLL )
// when string obf glow?
.rdata:000000018009F4E8	0000000A	C	(unknown)
.rdata:000000018009F560	0000000F	C	bad allocation
.rdata:000000018009F588	00000033	C	https://anticheat.glowogfn.com/v1/anticheat/report
.rdata:000000018009F5C0	00000023	C	glowjacobandkabra213123213mrduckkk
.rdata:000000018009F678	00000011	C	http://localhost
.rdata:000000018009F690	00000011	C	http://127.0.0.1
.rdata:000000018009F6A8	0000000D	C	http://[::1]
.rdata:000000018009F6B8	00000009	C	https://
.rdata:000000018009F6E0	00000007	C	\\u%04x
.rdata:000000018009F6E8	0000000D	C	unsigned_dll
.rdata:000000018009F6F8	0000000D	C	imgui_module
.rdata:000000018009F708	00000010	C	injector_module
.rdata:000000018009F718	00000011	C	injector_process
.rdata:000000018009F730	00000013	C	suspicious_process
.rdata:000000018009F748	00000015	C	injected_mouse_input
.rdata:000000018009F768	0000000D	C	\"timestamp\":
.rdata:000000018009F780	0000000D	C	\"processId\":
.rdata:000000018009F798	00000009	C	\"hwid\":\"
.rdata:000000018009F7A8	00000016	C	\"deviceFingerprint\":\"
.rdata:000000018009F7C0	00000010	C	\"encryptedIp\":\"
.rdata:000000018009F7D0	0000000A	C	\"email\":\"
.rdata:000000018009F7E0	0000000E	C	\"accountId\":\"
.rdata:000000018009F7F0	0000000D	C	\"username\":\"
.rdata:000000018009F800	0000000C	C	\"details\":\"
.rdata:000000018009F810	0000000C	C	\"suspect\":\"
.rdata:000000018009F820	0000000B	C	\"reason\":\"
.rdata:000000018009F830	0000001A	C	\"type\":\"anticheat_alert\",
.rdata:000000018009F8D8	00000009	C	\"event\":
.rdata:000000018009F8E8	0000000A	C	\"nonce\":\"
.rdata:00000001800A0808	00000034	C	Unsigned or untrusted DLL loaded into game process.
.rdata:00000001800A0840	00000041	C	ImGui-related rendering module detected inside the game process.
.rdata:00000001800A0890	00000040	C	Injector or cheat-tool module detected inside the game process.
.rdata:00000001800A08D0	00000047	C	High-confidence cheat-related module detected inside the game process.
.rdata:00000001800A1088	00000028	C	Known suspicious process name detected.
.rdata:00000001800A10B0	00000041	C	Process path contains high-confidence cheat automation keywords.
.rdata:00000001800A1100	00000046	C	Topmost click-through overlay + suspicious module signature detected.
.rdata:00000001800A1150	0000004B	C	Topmost click-through overlay behavior detected (possible ESP/AI overlay).
.rdata:00000001800A11A0	00000057	C	Suspicious process module detected (high-confidence automation/input spoof signature).
.rdata:00000001800A1200	0000005B	C	Suspicious process module detected (generic AI/runtime signature with suspicious context).
.rdata:00000001800A1260	00000021	C	ms while game window was focused
.rdata:00000001800A1288	00000021	C	 injected mouse input events in 
.rdata:00000001800A12B0	0000000A	C	Detected 
.rdata:00000001800A12C0	0000001E	C	 consecutive anti-cheat ticks
.rdata:00000001800A12E0	00000006	C	 for 
.rdata:00000001800A12E8	00000021	C	Injected mouse movement detected
.rdata:00000001800A1310	00000009	C	username
// some urls related to their server
https://anticheat.glowogfn.com/v1/anticheat/report
https://backend.glowogfn.com/fortnite/api/cloudstorage/system/DefaultInput.ini
https://backend.glowogfn.com/fortnite/api/cloudstorage/system/DefaultGame.ini
https://backend.glowogfn.com/fortnite/api/cloudstorage/system/DefaultRuntimeOptions.ini
http://backend.glowogfn.com:443
https://backend.glowogfn.com/account/api/oauth/token
https://backend.glowogfn.com/hotconfigs/v2/livefn.json
https://backend.glowogfn.com/fortnite/api/cloudstorage/system/config
https://backend.glowogfn.com/fortnite/api/cloudstorage/system
// prob localserver of glow idk
http://localhost:35783/api/auth/egl/users
http://localhost:35783/api/auth/egl/login/exchange
```
i'm lazy to find more shit. but i put a bypass in release. enjoy!
