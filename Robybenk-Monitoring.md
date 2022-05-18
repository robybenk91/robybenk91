Scriptku pertama : 
ON UP

:local nama "$user";
:local bot "5181013264:AAFzIjkiTLbeaTvJREgVOm2AqQAOs-oJqrY";
:local chat "2043577935";
:local ips [/ppp active get [find name=$nama] address];
:local up [/ppp active get [find name=$nama] uptime];
:local caller [/ppp active get [find name=$nama] caller-id];
:local service [/ppp active get [find name=$nama] service];
:local active [/ppp active print count];
:local datetime "Tanggal: $[/system clock get date] %0AJam: $[/system clock get time]";
:local lastdisc [/ppp secret get [find name=$user] last-disconnect-reason];
:local lastlogout [/ppp secret get [find name=$user] last-logged-out];
:local lastcall [/ppp secret get [find name=$user] last-caller-id];
/tool fetch url="https://api.telegram.org/bot$bot/sendMessage?chat_id=$chat &text=\E2\9C\85 PPPoE LOGIN%0A$datetime%0AUser: $user%0AIP Client: $ips%0ACaller ID: $caller%0AUptime: $up%0ATotal Active: $active Client%0AService: $service%0ALast Disconnect Reason: $lastdisc %0ALast Logout: $lastlogout %0ALast Caller ID: $lastcall" mode=http keep-result=no;


ON DOWN
:local bot "5181013264:AAFzIjkiTLbeaTvJREgVOm2AqQAOs-oJqrY";
:local chat "2043577935";
:local lastdisc [/ppp secret get [find name=$user] last-disconnect-reason];
:local lastlogout [/ppp secret get [find name=$user] last-logged-out];
:local lastcall [/ppp secret get [find name=$user] last-caller-id];
:local active [/ppp active print count];
:local datetime "Tanggal: $[/system clock get date] %0AJam: $[/system clock get time]";
/tool fetch url="https://api.telegram.org/bot$bot/sendmessage\?chat_id=$chat&text=\E2\9D\8CPPPOE-LOGOUT %0A$datetime%0AUSER: $user%0ALast Disconnect Reason: $lastdisc %0ALast Logout: $lastlogout %0ALast Caller ID: $lastcall %0ATotal active: $active Client" keep-result=no;




Lalu coba matika salah satu client di simpel queve dan lihat telegram


Script kedua ku :


:local nama "$user";
:local bot "5181013264:AAFzIjkiTLbeaTvJREgVOm2AqQAOs-oJqrY";
:local chat "2043577935";
:local ips [/ppp active get [find name=$nama] address];
:local up [/ppp active get [find name=$nama] uptime];
:local caller [/ppp active get [find name=$nama] caller-id];
:local service [/ppp active get [find name=$nama] service];
:local active [/ppp active print count];
:local datetime "Tanggal: $[/system clock get date] %0AJam: $[/system clock get time]";
:local lastdisc [/ppp secret get [find name=$user] last-disconnect-reason];
:local lastlogout [/ppp secret get [find name=$user] last-logged-out];
:local lastcall [/ppp secret get [find name=$user] last-caller-id];
/tool fetch url="https://api.telegram.org/bot$bot/sendMessage?chat_id=$chat &text=\E2\9C\85 LOGIN%0A$datetime%0AUser: $user%0AIP Client: $ips%0ACaller ID: $caller%0AUptime: $up%0ATotal Active: $active Client%0AService: $service%0ALast Disconnect Reason: $lastdisc %0ALast Logout: $lastlogout %0ALast Caller ID: $lastcall" mode=http keep-result=no;

ON DOWN

:local nama "$user";
:local bot "5181013264:AAFzIjkiTLbeaTvJREgVOm2AqQAOs-oJqrY";
:local chat "2043577935";
:local lastdisc [/ppp secret get [find name=$user] last-disconnect-reason];
:local active [/ppp active print count];
:local datetime "Tanggal: $[/system clock get date] %0AJam: $[/system clock get time]";
:local active [/ppp active print count];
/tool fetch url="https://api.telegram.org/bot$bot/sendmessage\?chat_id=$chat&text=\E2\9D\8C Client: $user%0A$datetime%0ATotal Active: $active Clien" keep-result=no;
