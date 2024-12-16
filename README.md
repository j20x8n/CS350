java c
CS-350   -   Fundamentals   of   Computing   Systems 
Final   Exam 
Fall   2020 
Problem   1 The         nancial   institutions   at   the   Bank   Block   in   Downtown   Sector   B3   are   all   connected   to a   central   processing   hub.      Due   to   the   recent   rise   in   cyber-crime   (especially   after   Dec.      10,   2020),   the   banks   have   adopted   measures   to   harden   the   security   of the   hub   that   handles   all   the transactions.   From the outside, and average of 7 requests   arrive every   millisecond.    These   have   always   to   go   through   a   congestion   control   (S0)   system       rst.S0   is   a   single-processor   system   with   an   exponentially   distributed   service   time.    It   operates   with   average   service   rate   of   7   requests   per   millisecond.    Congestion   control   is   performed   by   setting a hard cap N   on the   number   of requests   at   the   S0   system.    Requests that   arrive when   N   requests   are   already   in   S0   are   simply   rejected.   Any   request   that   is   not   rejected   moves   on   to   be   handed   by   the   hub.An   accepted   request       rst   reaches   the   authentication   (S1)   system:    a   single-processor   system   capable   of servicing,   on   average,   8.33   requests   every   millisecond.   Typically,   20%   of requests   fail   authentication   and   their   processing   is   halted.    Valid   requests   advance   to   the   processing   server   (S2).    This   is   a   single-processor   system   capable   of   serving   a   single   request   in   around   0.1   ms.After   processing,   a   request   is   completed   and   leaves   the   system   with   40%   probability.      Al-   ternatively,   the   request   is   routed   to   a   post-processing   single-core   server   (S3)   to   determine   what   type   of   follow-up   request   needs   to   be   generated   to   complete   handling   of   the   current   request.   This   post-processing step requires on   average   0.15   ms.    Follow-up requests   can   be   of   two   types:   inter-bank   and   intra-bank.   An   inter-bank   follow-up   request   needs   to   go   through   authentication,   which   happens   only   in   30%   of the   cases.    Conversely,   an   intra-bank   request   can   go   directly   to   the   processing   phase   skipping   authentication   altogether.      Follow-up   re-   quests then follow the   steps   of normal   requests                   i.e.   they   can themselves   require   (inter-   or   intra-bank)   follow-up   requests   and   so   on.    But   under   no   circumstance   a follow-up   request   is   sent   back   to   S0.
(a)    [3   points]   Provide   a   diagram   of the   system   where   you   specify   the   models   to   be   em-   ployed to   solve the   system.    Explicitly   list   any   assumption you   are   making to   solve the   system   that   is   not   already   stated   in   the   description   above.
(b)    [7   points]   While   keeping   the   rate   of requests   from   the   S0   server   as   a   generic   param-   eter   λa   ,   compute   an   expression   for   the   average   throughput   (in   terms   of   requests   per   millisecond)   at   the   servers   S1,   S2,   and   S3.   Show   your   work   for   full   marks.
(c)    [3 points] Which server   (S1, S3, or   S3)   represents   the   bottleneck   of   the   hub?    Motivate   your   answer.(d)    [7   points] The   goal   is   to   maximize   the   overall   throughput   of   the   hub   while   preventing it   from   buckling-up   due   to   congestion.   For   this   purpose,   we   can   adjust   the   value   of N   at   S0.   Exploring   the   range   of values   between   2   and   10,   what   is   the   ideal   value   of N?
Problem   2 You   have   been   assigned   to   analyze   a   black-box   image   compression   co-processor.      You   are   trying   to   understand   a   few   important   characteristics   of   its   behavior   by   providing   in   input   a   few   images   of   di    erent    sizes   (in   KB).   For   each   experiment,   you   have   recorded   the   time   it   took   to   perform   image   compression   and   the   total   energy    (in   Joules)   consumed   by   the   co-processor to   perform   compression   over the   given   image.    You   have   also   measured that the   processor   consumes   exactly   0   Joules/sec   when   idle.    The   measurements   you   have   collected   are   reported   in   Table 1. 
# 
KB 
Time (ms) 
Energy (J) 

# 
KB 
Time (ms) 
Energy (J) 
1 
454 
11.5 
1.3 

11 
721 
9.6 
0.9 
2 
952 
4.6 
0.2 

12 
306 
25.4 
6.5 
3 
805 
21.7 
4.7 

13 
572 
17.9 
3.2 
4 
141 
70.3 
49.4 

14 
156 
75.1 
56.4 
5 
194 
15.9 
2.5 

15 
651 
42.6 
18.1 
6 
205 
11.2 
1.3 

16 
171 
43.3 
18.7 
7 
152 
76.6 
58.7 

17 
871 
13.4 
1.8 
8 
47 
51.2 
26.2 

18 
48 
31 
9.6 
9 
534 
16.3 
2.7 

19 
490 
59.3 
35.2 
10 
689 
15.5 
2.4 

20 
818 
17.9 
3.2 
Table   1:   Image   compression   measurements   acquired   on   black-box   co-processor.
(a)      [3   points] Based on the acquired   data,   can   we   conclude   that   the   compression   of larger   images   takes   longer?
(b)    [3 points] Based on the collected data, can we conclude that the compression of   smaller   images   yields   lower   power   consumption?    Recall   that   power   is   measured   in   Watts   as   the   total   consumed   energy   over   the   considered   time   window   (i.e.   Joules/second).
(c)    [5   points]   With   what   con    dence   we   can   build   a   士13   ms   con    dence   interval   around   the   mean   of the   image   compression   service   time?
(d)    [5    points]   Consider   a   sequence   of   image   compression   requests   that   arrive    (and   are   potentially   queued)   at   the   co-processor   under   analysis   with   an   average   rate   of   29.4   requests   per   second.   What   will   be   the   average   response   time   of a   generic   request?
Problem   3 The   chemical   plant   Wharmful   Corp.    receives   three   types   of   raw   materials   M1,   M2   and   M3   to be stored in special   pressurized   cabinets   C1,   C2,   and   C3.    Materials arrive   in   packages   Pi   ,   with   each   package   containing   a   given   type   of   material   indicated   with   Pi   (Mx).    The   material Mx can only be stored in Cx.   As they move on the   conveyor   belt,   they         rst   reach the   sorting   area   which   can   hold   up   to   4   packages.      Here,   a   robotic   sorter   can   re-arrange   the   order   of   the   packages.   The   sorted   packages   are   then   sent   to   a   robotic   arm   that   stores   them   into   the   corresponding   pressurized   cabinets.      Refer   to   the   Piazza   post   for   a   visual   overview   of   the   organization   of   the   plant.Your   job   is   to   devise   a   strategy   to   program   the   robotic   sorter.    We   know   the   following   about the   system.       (1)    the    sorter   always          lls   up   the   sort代 写CS-350 - Fundamentals of Computing Systems Final Exam Fall 2020Haskell
代做程序编程语言ing   area         unless   there   are   not   enough   packages   on   the   belt.       Thus,    initially    it   will   take   in   the          rst   4   packages;    then   as   one   is   pushed   out,   a   new   one   is   taken   in   and   so   on.   It   has   no   knowledge   of other   packages   outside   of   the   sorting   area;    (2)   the   three   pressurized   cabinets   C1,   C2,   and   C3   are   initially   closed   and   whenever   closed   they   maintain   a   pressure   of 32   psi,   64   psi,   and   96   psi   respectively;   (3)   any   cabinet   needs   to   be   depressurized   down   to   16   psi   before   opening   and   depressurizes   at   exactly   -16   psi   per   time   unit;   (4)   any   cabinet   will   re-pressurize   instantly   after   it   has   been   closed;   (5)   the   arm   can   pick   up   the   next   packet   and   bring   it   to   any   cabinet   in   a   single   time   unit;   (6)   only   once the   arm   has   brought   a   package   in front   of the   corresponding   cabinet, the   cabinet   can   start   de-pressurization;   (7)   after   a   cabinet   is   at   16   psi   it   can   be   opened   and   the   arm   can   store   the   current   package   instantly;   and   (8)   only   one   cabinet   at   a   time   can   be   in   depressurized   state,   so   when   a   cabinet   initiates   depressurization,   the   system   automatically   closes   and   re-pressurizes   any   other   opened   cabinet.(a)    [6   points] De      ne   a   notion   of   readiness   to   adopt   FR-FCFS   as   the   sorting   strategy   with goal   of   minimizing   overall   storage   time.    After   that,   describe   and   motivate   the   order-   ing produced by   FR-FCFS if the packages   arrive   on   the   belt   in   the   following   sequence:
P1   (M2),   P2   (M3),   P3   (M1),   P4   (M2),   P5   (M1),   P6   (M3),   P7   (M3),   P8   (M1),   P9   (M2),   P10   (M1),   P11   (M3).   You   do   not   need   to   draw   the   time   plot   of the   system   in   operation.
(b)    [6   points]   By   using the   same   notion   of readiness   de    ned   above,   de    ne   a   new   strategy   that   (1)   still   prioritizes      ready         packages   but   that   (2)   tries   to   minimize   waiting   time when   no   ready   packages   are   available   in   the   sorting   area.       Once   again   describe   the   ordering produced by the new strategy   with   the   same   arrival   sequence   provided   above. 
(c)    [6    points]   Compute   the   total   amount   of   time   for   the   system   to   fully   store   all   the   11   packages   under   the   two   policies.    No   need   to   provide   timed   graphs,   but   show   your   reasoning.   You   can   also   assume   that   sorting   does   not   introduce   any   delay.
Problem   4 A sensor node needs to acquire and pre-process the data from 4 di    erentonboard sensors.   It is   crucial that pre-processing completes always before   a   new   data   sample   is   available   at   a   given   sensors   to   prevent   loss   of samples.    The   sensors   are   the   Gyroscope   (G),   Magnetometer   (M),Accelerometer   (A),   and   Baroscope   (B).   The   gyroscope   produces   data   at   a   rate   of   200   Hz,   with   each   data   sample   requiring   2   ms   for   pre-processing   in   the   worst   case.    Pre-processing   for   the   magnetometer   takes   no   longer   than   1   ms   with   samples   being   produced   at   125   Hz.   A   new   accelerometer   sample   is   produced   every   19   ms   and   pre-processing   takes   at   most   4   ms.   Finally,   pre-processing   a   barometer   sample   takes   at   most   6   ms,   but   the   sampling   period   is   con      gurable.
(a)    [6   points]   Without   drawing   the   schedule,   perform   a   back-of-the-envelope   calculation to   determine   a   suitable   con    guration   for   the   sampling   period   of   the   barometer   such   that the system always operates correctly under RM. For this part, consider only values   of periods   that   are   integers   when   expressed   in   milliseconds.
(b)    [6   points]   Because   the   calculation   above   returned   a   value   of   sampling   period   which   is   too   large,   you   decide   to   set   the   barometer   sampling   period   to   29.    Will   the   system   operate   correctly   under   RM?
(c)    [8    points]   You   decide   to   set   the   barometer   sampling   period   to   30   ms   and   stick   to   RM.   You   notice   however   that   once   in   a   while   (very   rarely)   the   pre-processing   of   the   accelerometer takes   5 ms instead of its   nominal   4   ms   worst-case   execution   time.    When   this   happens,   the   system   can   still   operate   correctly   if the   faulty   accelerator   pre-   processing   job   is   killed   when   it   misses   the   deadline.    Killing   any   other job   is   not   acceptable.    Also,   you   can   apply   a   utilization-preserving   transformation   to   all   or some   of your   tasks.    Speci    cally,   you   can   release   any   pre-processing   task   twice   as   fast   but   only   perform   half of the   required   processing   in   each   release.   Explain   how   you   can   make   the   system   operate   correctly   under   RM.
Problem   5 Two   processes,    namely   the   Printer   and   the   Shifter,    co-operate   to   respectively   print   and   update   the   value   of   an   array   of   integers   that   has   a         xed   size   of   5   elements.       The    code   executed   by   the   Printer   process   is   provided   in   Listing 1;   the   code   of   the   Shifter   process   is given in   Listing 2. If a variable has the   same   name   in   both   processes,   it   is   to   be   considered   a   shared   variable.   A    [FRAGMENT    x]    statement   in   the   code   refers   to   additional   lines   of code   (a   fragment) to be inserted in   place   of the   statement.    At the   beginning   of time,   both   processes   start   executing   at   their   start   line   and   will   not   run   again   once   they   reach   their   end   line.   The   initial   state   of   the   shared   data   structures   is   as   follows:      array      =      [4,    9,    5,    3,    6] ;   queue      =      [8,    1,    7,    2]      (NOTE:   8   is   at   the   head   of   the   queue.)
(a)    [4   points]   Assume   that   P2   and   S2   are   empty   and   that   (a)   fragment   P1   expands   to wait(go);   and   (b)   S1   expands   to   if(queue   .empty()){signal(go);}.      Here,   go   is   a   semaphore   initialized   to   0.   What   is   the   maximum   value   that   could   ever   be   printed   at   line   13   by   the   Printer   process?
(b)    [8   points] Assume   that   (a) fragment   P1   and   S1 expand   to   wait(m);   and   that   (b)   P2   and   S2   expand   to   signal(m);.    Here,   m   is   a   semaphore   initialized   to    1.    What   is   the   maximum   value   that   could   ever   be   printed   at   line   13   by   the   Printer   process?
(c)    [8    points]   Assume   that   fragments   P1,   P2,    S1,   and   S2   are   all   empty.      What   is   the   maximum   value   that   could   ever   be   printed   at   line   13   by   the   Printer   process?



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
