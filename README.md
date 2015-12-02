// Primary Commands
con_enable "1"
bind § "showconsole"
cl_righthand 1

// Bindings
bind v +voicerecord
bind f1 "autobuy"
bind f3 "buy flashbang;buy smokegrenade;buy flashbang;buy hegrenade"
bind f4 ignoremsg
bind f "+lookatweapon"
unbind i //So it doesn't interfere with showing the loadout.

// No Tutorial or Info Messages
gameinstructor_enable 0 
cl_showhelp 0 
cl_autohelp 0 
cl_disablefreezecam 1
cl_disablehtmlmotd 1

// Rates
rate 128000
cl_cmdrate 128
cl_updaterate 128
cl_interp_ratio 1
cl_interp 0
cl_lagcompensation 1
cl_predict 1
cl_predictweapons 1

// Video
mat_monitorgamma 1.6
mat_monitorgamma_tv_enabled 0

// Sound
voice_scale 0.4
snd_mixahead 0.05
snd_musicvolume 0

// Net
fps_max "0" // Setting this to 0 will uncap it.
fps_max_menu "144" // Set this to the monitors Hz
net_graph "1" //Enables Net Graph
net_graphheight "990"
net_graphmsecs "400"
net_graphpos "2"
net_graphproportionalfont "0" // Makes the Net Graph font smaller
net_graphshowinterp "1"
net_graphshowlatency "1"
net_graphsolid "1"
net_graphtext "1"
net_maxroutable "1200"
net_scale "5"
net_steamcnx_allowrelay "1"

// Bobcycle
cl_bob_lower_amt 5
cl_bobamt_lat 0.1
cl_bobamt_vert 0.1
cl_bobcycle 0.98
cl_viewmodel_shift_left_amt 0.25
cl_viewmodel_shift_right_amt 0.25

// Viewmodels
viewmodel_offset_x 1
viewmodel_offset_y 2
viewmodel_offset_z -2
viewmodel_fov 64
viewmodel_presetpos 4

// Other
hud_scaling 1
r_drawtracers_firstperson 0 // hides bullets
cl_viewmodel_shift_left_amt 0 //These two removes the shifting of the arm when crouching down
cl_viewmodel_shift_right_amt 0
lobby_voice_chat_enabled 0 // Microphone off in lobby
cl_use_opens_buy_menu "0" // Disables E from opening buy-menu.
mm_dedicated_search_maxping 50

// Mouse
m_forward 1
m_rawinput 1
m_mouseaccel2 0
m_mouseaccel1 0
m_customaccel 0
m_customaccel_max 0
m_customaccel_exponent 0
m_customaccel_scale 0

// Crosshair
cl_crosshair_drawoutline "1"
cl_crosshair_dynamic_maxdist_splitratio "0"
cl_crosshair_dynamic_splitalpha_innermod "1"
cl_crosshair_dynamic_splitalpha_outermod "0.300000"
cl_crosshair_dynamic_splitdist "7"
cl_crosshair_outlinethickness "1"
cl_crosshairalpha "255"
cl_crosshaircolor "2"
cl_crosshaircolor_b "0"
cl_crosshaircolor_g "255"
cl_crosshaircolor_r "0"
cl_crosshairdot "0"
cl_crosshairgap "-1"
cl_crosshairgap_useweaponvalue "0"
cl_crosshairscale "0"
cl_crosshairsize "4"
cl_crosshairstyle "4"
cl_crosshairthickness "0"
cl_crosshairusealpha "1"
cl_fixedcrosshairgap "1000"


// Hud Modification (From Patch 1 May Yay)
hud_showtargetid "1" //Enables display of target names
cl_hud_bomb_under_radar 1
cl_hud_color 7
cl_hud_radar_scale 0.9
cl_radar_scale 0.3
cl_radar_always_centered 0
cl_hud_playercount_showcount 0
cl_hud_playercount_pos 1
cl_hud_healthammo_style 1
cl_hud_background_alpha 0
cl_loadout_colorweaponnames 1 //Show different colors for each weapon quality
cl_radar_icon_scale_min 0.8
cl_showloadout 1 //Don't fade out the loadout
hud_scaling 1
safezonex 0.85
safezoney 0.85

// Show netgraph when checking scoreboard
alias "+scorenet" "+showscores; net_graphheight 0"
alias "-scorenet" "-showscores; net_graphheight 9999"
bind "TAB" "+scorenet"

// Display Damage with Switch Script
alias displaydamage "displaydamage_on"
alias displaydamage_on "con_filter_text Damage Given To; con_filter_text_out Player:; con_filter_enable 2; developer 1; playvol buttons\blip1 0.5; alias displaydamage "displaydamage_off""
alias displaydamage_off "con_filter_enable 0; developer 0; playvol buttons\blip2 0.5; alias displaydamage "displaydamage_on""
bind "f5" "displaydamage"

// Show crosshair Settings
alias "a1" clear
alias "a2" echo "*********************************************";
alias "a3" echo "YOUR CURRENT CROSSHAIR SETTINGS;"
alias "a4" echo "*********************************************";
alias "a5" developer 2
alias "a6" con_filter_enable 1
alias "a7" con_filter_text cl_crosshair
alias "a8" host_writeconfig //
alias "a9" con_filter_text cl_fix
alias "a10" host_writeconfig //
alias "a11" developer 0
alias "a12" con_filter_enable 0
alias "a13" showconsole
alias "showcrosshair" "a1;a2;a3;a4;a5;a6;a7;a8;a9;a10;a11;a12;a13"
bind ins "showcrosshair"

// Show viewmodel Settings
alias "b1" clear
alias "b2" echo "*********************************************";
alias "b3" echo "YOUR CURRENT VIEWMODEL SETTINGS;
alias "b4" echo "*********************************************";
alias "b5" developer 2
alias "b6" con_filter_enable 1
alias "b7" con_filter_text viewmodel
alias "b8" host_writeconfig //
alias "b9" con_filter_text view_punch
alias "b10" host_writeconfig //
alias "b11" developer 0
alias "b12" con_filter_enable 0
alias "b13" showconsole
alias "showviewmodel" "b1;b2;b3;b4;b5;b6;b7;b8;b9;b10;b11;b12;b13"
bind del "showviewmodel"

// Jump Throw Script
alias "+jumpthrow" "+jump;-attack"
alias "-jumpthrow" "-jump"
bind "mouse5" "+jumpthrow"

// How to pick up a specific grenade (E = HE) (Q = FLASH) (1 = SMOKE) (2 = FIRE) (3 = DECOY)
alias altE1 "use weapon_flashbang"
alias altE "bind q altE1" //IF YOU USE FRENCH KEYBOARD, CHANGE "Q" TO "A"
alias alt11 "use weapon_smokegrenade"
alias alt1 bind 1 alt11
alias alt22 "use weapon_molotov; use weapon_incgrenade"
alias alt2 bind 2 alt22
alias alt33 "use weapon_hegrenade"
alias alt3 bind e alt33
alias alt44 "use weapon_decoy"
alias alt4 bind 3 alt44
alias alt55 "buyanddrop"
alias alt5 bind g alt55
alias alt66 "disablevoice"
alias alt6 bind v alt66 //CHANGE THE "V" TO YOUR VOICE KEY
alias defE "bind e +use"
alias def1 "bind 1 slot1"
alias def2 "bind 2 slot2"
alias def3 "bind q lastinv" //IF YOU USE FRENCH KEYBOARD, CHANGE "Q" TO "A"
alias def4 "bind 3 slot3"
alias def5 "bind g drop"
alias def6 "bind v +voicerecord //CHANGE THE "V" TO YOUR VOICE KEY
alias +altbinds "alte; alt1; alt2; alt3; alt4; alt5; alt6"
alias -altbinds "defE; def1; def2; def3; def4; def5; def6"
bind alt +altbinds

// Buy and drop
alias "buyanddrop" "buy ak47; buy m4a1; buy m4a1_silencer; slot1; drop"
// This script is combined with the extra hotkeys for grenades.

// Disable in-game voice + no rebinds needed
alias "disablevoice" "voice_chat"
alias "voice_chat" "chat_1"
alias "chat_1" "voice_scale 0.5; playvol buttons\blip1 0.5; alias voice_chat chat_0"
alias "chat_0" "voice_scale 0.0; playvol buttons\blip2 0.5; alias voice_chat chat_1"

echo ",;,,,;,;,;,;,;,;,;;;;L                ...:,;;L;L;FyjjEhK5hKOO8S8SESpObb8OBOpb88bbpO8bb8BbQBQBQQgQQBQBQBQBQbbGpOGnzLrL;,  ,,:.... ..:L;;,;;;;,;;;;;,;;;,;,;,;,;,;"
echo ";;;;;;;;;;;;;;;;;;;;L;      .         :;;;rzyyZFFZGOpG8OQ8Bbb8QBB8bBQBgg8OBbBOBBQBQQgggggg@g@g@g@@@@@@@@@@@g@ggQb5yL;;;:. .         ,zc;;;L;;;;;;;;;;;;;;;;;;;;;"
echo ",;,;,;,;,;,;,;;;,;,;;,     .   . .   ,;;;cLFzjFzyh3hKShS5OGES88bpGEOhGGGnGhEEOE8bQQQBQBQQgQgQgQQQgQQBQQgQgQQQQBQbOyL:: .,:.  ,;;;;   ;:;;;;;;;,;,;;;;;;;,;,;,;,;"
echo ";;;,;,;,;,;,;,;,;,;;L,      . ..,:::,,;;L;rLLF7cyZE5SSGoE5GE8pbbBSGEOpGhOp85O8BBgQgQgggQgQgggQgQgQQQgQQQgQQQQQQQQQBKr;:   .;cz5ShSL ...;L,;;;;;;;,;;;;;;;,;,;,;;"
echo ":;,;,;,;,;;;,;,;,;,;;;       ....,;;,;;;;LLrrzrzLyyZK55OE5hp8bBQpG5hOOhGE8bBbQQQBQQgQgQgggggggQgQgQQQgQgQQQgQQQQBgQQpn;;.  .,.:rF7y,   .;;;;;;;;;;;;;;;;;;,;,;,;"
echo ";;;,;,;,;,;,;,;;;;;;;;.   . .   ..,;;,;,;;LLz;7zcznZhoOGOE8bBbQQBEEKOGOE88QQBBBbQBgQgggQgggQgQgQgQgQgQgggBQQQBQBQBQQgB5LL;;.. . :;;;c;L;;:;;;;;,;;;;;;;;;,;,;,;;"
echo ",;,;,;,;,;,;,;;;;;,;;L.    .   ..,,;,;,;;;;;;L;cLjnhK558OGEBbBQQQbGpEOO8pbQQOBbQQgggggg@ggQgQgBQQggggQQgQQBQQQQQBQBQQgQby,,7  .   ;z8@g@h.:;;;;;,;;;;;,;,;;;,;,;"
echo ",;;,;,;,;,;,;,;,;;;;;;;   .   ..::;;;,;,;;;;;,;;rzZKEhEObG8pbbQQgb8ObOGpBbQb8pbpQQgg@ggggQQ8BBB8QQQQQBQQgQQQQBQQQQQQg@@gO  :      3j;;LE@7.,;;;;;;;;;,;;;;;,;;;;"
echo ",;,;,;,;,;,;;;;;;;;;;;L,   .   ..,,;;;;;;;;L;;;;;zzZoS5O8b8bEbbQgQGpOB8SOOS5j5nh5ych53SpGOGESOSEoOOO5O8BbQBQQgQgg@@@gS::;K8G,,;L,nQQoy. Sg:,,;;;,;;;;;;;,;,;,;,;"
echo ";;;,;,;,;,;,;;;,;,;;;;;;       .,:,,;,;;;;;;L;LLLLyoESOOp8bO8bbBg83SpGB5ncr;;;;;L:,;,,;,,,;rnnpphnKKS5OOpQgQgg@@@b7   ;p@BQbKLjQbQgQb8Z.c@L:;;;;;;;;;,;,;,;,;;;;"
echo ",;,;,;,;,;;;,;,;;;;;;;;L,      ..,:,,;,;;;;;;LLrLzcyZhGOEp5hpb8QBOcKEOE5;LLL;L,,;;,:.,:,:;,;;;ro8gQgBQQQQgg@gQZ.   rb@ggQBOQbObQggQgBBO;,@F:;;;;;;,;;;;;;;;;,;,;"
echo ",;;,;,;,;,;;;,;,;;;,;;;;r:      ::,.,:,,L;L;L;;;;,;;;;;;j3oy3KOGBn;yOO8pSz7LFryjL;zKGE88BBgg@@@B8EB@@BQg@QG;   .ng@@@QQBB8pBQBg@@ggggB8;L@c.;;;;;,;;;;;,;,;;;,;;"
echo ":;,;,;,;,;,;,;;;;;;;;;;;;L.    ..:::.::,;;,;;;,:....   .:,;;;Ljhn;,yhBQ@ggbGzZ3Lnb88OpG88BBQggg@gg3yKppF.   ,8@@g@gQBQbB88ObQgoy8BBQBQBzOb.,,;,;;;;;;;,;,;;;;;,;"
echo ";;;,;,;,;,;;;,;,;;;;;;;;;;L     .:::,:. ....,.. ..,:,,;,:...;;c;:,LzSb@@@g@bp7.jSKSKF;. .  ;. ,,;;yc;oE.:Lb@@@@QQBQBQbBbb888QE .zSb8BQgGgL.,;;;;;;;,;;;;;;;,;,;;"
echo ",;,;,;,;,;,;;;;;;;;;;;;;;LL.     :,,,,.      .,LFhOb8BQQO8h3z7;;..,L,;;;FOphByhy,;:. .;;.  ;:;FZEbBQ8QBQQ@ggQQQgBBbQBQBb8B88bbz:;noOOBgQQ,.;,;;;;;,;;;;;;;,;;;,;"
echo ",;;,;,;,;,;,;,;;;;;;;;;;;,,:.     .:,;,.....;LFjKZ5SShjLF7zrL;. c.  ,r7KBB8LLr8S7;;;;LcLcrjSQg@@@gQ8bpbbbQgQgQQQQBbbBBBbBbB88Q@bz;LyohQQQ::,;;;;;;;,;;;;;;;,;;;;"
echo ":;,;,;,;,;,;,;,;,;;;;;;;;: ......    :::.. ;,;;;::..   y.:       . .ZbE8Q@@g.,y38BhjyyFZZES8p8pB8bbQbbQQQQQQQQQQBQbbbQBQbBbbO8g@g5L7ZOQgQ;.;,;;;;;;;;;,;;;,;,;,;"
echo ",;;,;,;,;,;,;,;,;,;,;;;;L.    . . :.      :,          .zLcr;;;:... :yKEbQQ@@B.p5,3bOOSGhOOOSOGppbQgBBQgQQQQBQQQQQbb8BQQBBbBbbhBg8c;zObgBg,,,;,;,;,;,;;;;;;;;;,;;"
echo ",;,;,;,;,;,;;;,;;;;;;;;;;;      ...,::..  ,c   ..,,;;zyn3oZnc;.... ,;ypbQQg@gg;Go3ZohOEO5OOO8b8ObQBBQQBQQQQQQQBQBB8bpQBQQQBBb8SShppQQQpgS.:;;;;;;;;;,;;;,;,;,;,;"
echo ",;,,;,;,;,;,;;;,;;;;;;;;;;;.    ...:::,,;:.K;.,,;Lz7yyyzyrrLL;;....;;jbBgggg@@@8ggbhEhhK5ZEGOSKySGb8bbBbQQgQgQQQQbQBBpQQQQQBB8phbQgQQpB@z.,;;,;;;;;,;,;,;;;,;,;;"
echo ",;,;,;,;,;,;,;,;,;;;;;;;;;;r;.   ....:,;;;:;OF.:,;;LrrLr;L;L;;::::;;;GBgggggggg@@@ggbbOOEEhhoh5OObbBBQQQQQQgQQQQQQQQBBBQQQBB8BpOQgBQbQg8c;,;;;;;;;;;;;,;,;;;,;,;"
echo ",;,,;,;,;,;,;;;;;;;;;;;;;;;;LL;.......:,;;r;;hG7L;L;rLLLc;r;;,,,;;;,;nbQgggQgggg@g@QQ8B88p8O8OBbbbBBQQgggQgQQQQQQBQQQbQbQQQbQbBEbQQQQQ8;,;;;;;;;;;;;;,;;;,;;;,;;"
echo ",;,,,;,;,;,;,;,;;;,;;;;;;;;;;;;r:  ...:;,;;;;;75hKFyzyFzLc;;;L;L;;;;;yGbQgQgQgQgggQQOo3ESSG8O8pb8QBQBgQgQgQgBQBQBQBQBbBQBQQQbBBbOQbbbgn .;;;;;;;;;;;;;;;,;;;,;,;"
echo ",;;,;,;,;,;,;,;,;,;;;;;;;;;;;;;;L.. ..::;:;;L;L;LcjyZyZFyzFzzL;,,;;,rjEpQQgQQBgQQBBBQ5r;;LFnK5OOb8bbQBQQgggQQBQBQQQQQbBBQbQQQBB8p8BbQ@O .;;;;;;;;;;;;;;,;;;,;,;;"
echo ",;,;,;,;,;,;,;,;,;,;;;;;;;;;;;;;;;...:.::;,;;LLyZShGGESEKKjz;,..:;;;;ZSbQgQQQQQQ8bbQQQn;,::;;7ySEppbbBQgQQBQQQbQQQQQQQbBQQBQBQbBObg@@@.::;;;;;;;;;;;;;,;;;;;,;,;"
echo ";;,,;,;,;,;,;,;,;,;,;,;;;;;;;;;;;;,...:.::;,;;zF535oEo5jycL,.  :;,;,;yppQQgQgQQQQQgggQ8GGy;::,;roS8p88QQQQQBBBQ8QQQBQQQ8QQQBQBB8bObEc  ;;;;;;;;;;,;;;,;,;,;,;,;;"
echo ",;,;,;,;,;,;,;,;,;,;,;;;;;;;;;;;;;;,.:...::;;L7zj5K5K5ZyrL,.   L;;;;;ch8bQggQgQgggQbObBQBbEj;;:;;ynEE88BBQBQBQQBBQQQBQbQBQBQBBbB8B;    :,LLL;;;;;;,;;;;;,;,;,;,;"
echo ",,;,,,;,;,;,;,;,;,;,;;;;;;;;;;;;;;L;..:...::;;z7jZ5noK5Zz;;.  :;;;;;zFS8BQgg@QgBbOEnOQgQgBBpOycLL;c7yKGO88BbQBQBQBQQQQQBQBQbQBQbbbO,    ..::,;L;L;;;;;;,;,;,;,;,"
echo ",;,;,,,;,;,;,;,;,;;;,;,;,;;;;;;;;;;;.......,,LLz7Z333oKEnz;;:;,,:::;LKSp8QggggBbQQQQbQQgQQ8b8b53nc7KK3opOBBQBQBQbBBQBQBQQQBQbQbB8bpby          ..;;;;;;;,;,;,;,;"
echo ";,,,;,;,;,;,;,;,;,;,;,;,;;;;;;;;;;;;: :.,.::;;LLyy5ZKKh5oFF;;;;;;.. .;ynhObBBZ3SOpBbQQQQQbB8bBQ8QE3KO88ObBQQQBQB8BQQgBQQQbBbBBB8b8pOQO.           .,L;;;;,;,;,,;"
echo ",;,,,,,;,;,;,;,;,;,;,;;;,;,;;;,;;;;L, ..::..:;;rFZZo3ESh3ncrLL;;;;.....,;znhz;zny5O8bQQQBQQQBQQgB8ozy55nhQBQBQBQbBBQQQBQBBb88b8b8bpEOB8.            .;;;,;,;,;,;"
echo ";,,:,,,,;,;,;,;,;,;,;,;,;;;,;;;;;;;;L...::...:;;cLjZ5oSo53F;;;;,;,;;;;LLyyh5SS5nEOBbgg@@@@@@@Q8Sy7y7y;;LSBQbQBQQQbQBQQQBB8bpB8Bbb88SEGbb;            .;;;,;,;,;;"
echo ",;,,,;,;,;,;,;,;,;,;,;,;;;;;;;;;,;;;;; ..:....,;;zjSo5KoZ5jL;;;;;;;L;zFE8BQQBQBb88p8OGo3jz;;;73EKno8EF;38QQQBQQQQB8BBQbQbb8bbb8b8bpEKGObBL          ...;;;,;,;,;"
echo ",,,,;,,,;,,,;,;,;,;,;,;;;;;,;,;;;,;;;;. ..:...,,;rno3j3ZKjzL;;;;;;r7jn35G5Oh5KKjZL; ,...::LhQggggbbO5y5GBBQQQQQBQBQbQBB8b8b8B8B8bpbSEGOGbQ;         ....,;;;;,,,"
echo ":;,,,;,,,;,;,;,;,;,;,;,;;;;;;;;;;;;;;L,........,;FFLLnjjynFL,,,;;L;;;;::   ..  ,LjnKGBQgg@@@gQQQQQBbhoEbBQBQBQBBBQBQBB8bpb888bbb888S58EpO8pL.      ......:,;;;,;"
echo ",,,,,,,,,,,,;,;,;,;,;,;,;,;,;;;;;;;;;;L. ...:...;zS;LnonK3KL;:.         .:;cjcFZpbQg@ggggQgQQbQQQQQbbG88BBQBQBBbQbBbB8bO8pb8BbB888boSpOOpO8cL:    ....: ....,;;;"
echo ":;,,:,:,:,,;,;,;,;,;,;,;,;,;,;;;,;;;;;;;. ...,. :7nZzohpGOE5y;,;::...:;y5pO888O88BBQQQQQBQQQbQbQQQQQBB8B8bpB8BBB8Q8b8bOp8b8BbBbbO8Ohh8O8ObEz;;     ..,:. ......,"
echo ",,;:,:,,;,,,;,;,;,;,;,;,;,;,;,;;;;;;;;;;; ...:;. :LjyrSObpGhSzL;L;;;,.,;FjooEhOE5KEG8bQBQQQQQBBQQQgQQBQbb8b88bQ888Bp8O88bpb8b88O88OnGE8EOOEL;:    ..:::.. ......"
echo ":;,;:,:,,,,,,,,;,;,;,;,;,;,;,;;;,;,;;;;;;,  ..:;. .Lz77SpbpOZF7c;L;,...:,LcnzLLKn3n5OBBQBQQgBQBBbQQgQQBQ8b8QbBBB8b8bO888pb8b88pb8853EOOOGOK;..   .....::........"
echo "::,:,:,:,:,,,,,,,,,,;,,,;,;;;,;,;;;,;;;;;;:   .,;. .;;LyhhphS7Lr7LL;;,,:;;jK5zyKOEGS88bBQBBbb8BbQBQBQQQQQbbbb8bbbp8p8O8Ob8bpb88ObGSKEGpSpSj.    ................"
echo ":;:,:,:,:,:;,;,;,;,;,;,;,;,;,;,;,;,;,;;;;;L.   .:;.  ,;7y35Go5;Lc7L7;L;Lco5Go53EEShOG88bO8OppbbQbBQQBQQQbBbB8B8b888b88Ob8B8b8pp8GpSS5pGOGS;.     ..............."
echo ",:,:,:,:,:,,;,,,,,;,;,;,;,;,;,;,;,;;;;;,;;;;.   ..,.. .,LLFzyyF;rLrcyzyz3nKojFF7yjKoEObGESpO88QBQQQBQQQBBbBbBbb88Ob8b8b8B88pbObGOOGEOOGoOy.     ................"
echo ":,:::,:,:,:,:,:,,,,,,;,;,;,;,;,;,;,;;;,;,;,;;. .   ... .:::;;L;rcz;nZ33on7;;;LLnKSSpG8p88b8BbQBQQQBQBQBB8bpb8b88Ob8b8bbBpb8b88G888GOGOEG3;     ................."
echo ":::.,:,:,:,:,:,:,,,,;,;,;,;,;,;,;,;,;,;;;,;;L;. .   ........:,;;rLcz3h5rL;;;Fzo5OS8Ep8bpBBBBQBQBQBBbB8b8b8bpbO88b8B8b8b8bOb88O8O8pGG8SG3L     ....:............."
echo ":,.::::::,:,:,:,:,:;,,,;,;,,,;,;,;,;,;;;,;,;;;;. . . ..... . .:;;L;LLycL;LLynSSOEEhO8B8bbQBQBQQQBQ8bppO88b8b8b8B88pb88pBpbO8O8p8O8E8hE57.     .................."
echo ":::.,:,:,:,:,:,:,:,:,,,,;,;,;,;,;,;,;,;,;,;,;;;;. ... . ..... ..,,;;;;cL;;7nhZOEEEpO8bB8BbQQQQQbQb8EpO88bO8p88B8b88p8p8pbpbpbp8O8O8OpEj.    . . ......... ......"
echo ".,.:.::,.,:::::,:,:,:,:,,;,;,;,,,;,;,;,;,;,;,;;c;  ... . ....  ..,,;;;;L;LLyjoEOhSOpObOb8BbQbBbbpphGO8pB8b8pb8bbp8O8O8O8p888p8Opp8ObOo.    . . ........... ....."
echo ":::.,.::::::::,:,:,:,:,:,,,,,,;,;,;,,,;,;,;,;;LL   .. ... . ...  .::;,;;L;LLzyOK5oGSOGOpb8bO8GOGh5
echo "PRAISE OUR LORD GABEN!"
