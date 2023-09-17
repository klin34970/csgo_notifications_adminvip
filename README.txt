I - Description

I made this plugin for my community Zombie4Ever.eu and was allowed to share it.
Notifications connection for admin and vip with sounds and/or messages.
All sounds placed on the"addons/sourcemod/configs/drapi/join_sounds.cfg"will be automatically downloaded. You can Enable/Disable all sounds and message for each events. Also player can Enable/Disable all sounds and message for each events too by typing in chat!js.

II - Cvars

 
"drapi_join_sounds_join_admin_tchat"     "1" - "Enable/Disable Admin message join"
"drapi_join_sounds_join_vip_tchat"     "1" - "Enable/Disable Vip message join"
"drapi_join_sounds_join_admin_sound"     "1" - "Enable/Disable Admin sound join"
"drapi_join_sounds_join_vip_sound"     "1" - "Enable/Disable Admin sound join"
 
"drapi_join_sounds_leave_admin_tchat"     "1" - "Enable/Disable Admin message leave"
"drapi_join_sounds_leave_vip_tchat"     "1" - "Enable/Disable Vip message leave"
"drapi_join_sounds_leave_admin_sound"     "1" - "Enable/Disable Admin sound leave"
"drapi_join_sounds_leave_vip_sound"     "1" - "Enable/Disable Vip sound leave"
 

III - Confis

 
"Sounds"
{
    "Sounds"
    {
            "AdminJoin"
        {
            "1"                 "join_sounds/admin_join_dubstep.mp3"
            "2"                 "join_sounds/admin_join_scooter.mp3"
            "3"                 "join_sounds/admin_join_starwars.mp3"
        }
 
            "AdminLeave"                                     
        {
            "1"                 "join_sounds/admin_leave_announce.mp3" 
        }
 
            "VipJoin"
        {
            "1"                 "join_sounds/vip_join_samba.mp3"
        }
 
            "VipLeave"
        {
            "1"                 "join_sounds/vip_leave_baby.mp3"
        }
    }
}
 


Put your songs in the section you want, if there are more than 1 song it will choose randomly one.
All sounds will be automatically downloaded and precached.

IV - Make a .mp3

For play a .mp3 without error you need to:
Sample rate at 44100 hz
bitrate at 128kbps
Quality resampling at 128-point sinc

V - Flags

You can change the flags in the code if you don't use like us this following.
 
/***********************************************************/
/******************** CHECK IF IS A VIP ********************/
/***********************************************************/
stock bool IsVip(int client)
{
    if(GetUserFlagBits(client) &amp; ADMFLAG_CUSTOM1 
    || GetUserFlagBits(client) &amp; ADMFLAG_CUSTOM2 
    || GetUserFlagBits(client) &amp; ADMFLAG_CUSTOM3 
    || GetUserFlagBits(client) &amp; ADMFLAG_CUSTOM4 
    || GetUserFlagBits(client) &amp; ADMFLAG_CUSTOM5 
    || GetUserFlagBits(client) &amp; ADMFLAG_CUSTOM6)
    {
        return true;
    }
    return false;
}
 
/***********************************************************/
/****************** CHECK IF IS AN ADMIN *******************/
/***********************************************************/
stock bool IsAdminEx(int client)
{
    if(GetUserFlagBits(client) &amp; ADMFLAG_CHANGEMAP 
    /*|| GetUserFlagBits(client) &amp; ADMFLAG_RESERVATION*/
    || GetUserFlagBits(client) &amp; ADMFLAG_GENERIC
    || GetUserFlagBits(client) &amp; ADMFLAG_KICK
    || GetUserFlagBits(client) &amp; ADMFLAG_BAN
    || GetUserFlagBits(client) &amp; ADMFLAG_UNBAN
    || GetUserFlagBits(client) &amp; ADMFLAG_SLAY
    || GetUserFlagBits(client) &amp; ADMFLAG_CHANGEMAP
    || GetUserFlagBits(client) &amp; ADMFLAG_CONVARS
    || GetUserFlagBits(client) &amp; ADMFLAG_CONFIG
    || GetUserFlagBits(client) &amp; ADMFLAG_CHAT
    || GetUserFlagBits(client) &amp; ADMFLAG_VOTE
    || GetUserFlagBits(client) &amp; ADMFLAG_PASSWORD
    || GetUserFlagBits(client) &amp; ADMFLAG_RCON
    || GetUserFlagBits(client) &amp; ADMFLAG_CHEATS
    || GetUserFlagBits(client) &amp; ADMFLAG_ROOT)
    {
        return true;
    }
    return false;
} 