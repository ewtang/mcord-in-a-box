# mcord-in-a-box
Troubleshooting notes for mcord-in-a-box using Kubernetes

eric@ubuntu:~$ kubectl get pods -n openstack | grep -i crash
libvirt-7zg45                                  0/1       CrashLoopBackOff   6          17m

eric@ubuntu:~$ kubectl logs libvirt-7zg45 -n openstack
++ grep libvirtd
++ cat /proc/1/comm /proc/10/comm /proc/100/comm /proc/10051/comm /proc/10075/comm /proc/10115/comm /proc/10128/comm /proc/10137/comm /proc/10153/comm /proc/103/comm /proc/104/comm /proc/105/comm /proc/10516/comm /proc/1058/comm /proc/106/comm /proc/10622/comm /proc/1064/comm /proc/1080/comm /proc/1086/comm /proc/1090/comm /proc/1098/comm /proc/1099/comm /proc/11/comm /proc/11021/comm /proc/1104/comm /proc/1105/comm /proc/1106/comm /proc/1107/comm /proc/1108/comm /proc/1109/comm /proc/1110/comm /proc/1111/comm /proc/11266/comm /proc/11267/comm /proc/1154/comm /proc/11584/comm /proc/11660/comm /proc/1180/comm /proc/11915/comm /proc/12/comm /proc/12024/comm /proc/12025/comm /proc/12026/comm /proc/12094/comm /proc/12117/comm /proc/12122/comm /proc/122/comm /proc/12264/comm /proc/12352/comm /proc/12371/comm /proc/12405/comm /proc/12413/comm /proc/12428/comm /proc/12448/comm /proc/12464/comm /proc/12479/comm /proc/12517/comm /proc/12566/comm /proc/12591/comm /proc/12645/comm /proc/12662/comm /proc/12684/comm /proc/12701/comm /proc/12718/comm /proc/12741/comm /proc/12777/comm /proc/1290/comm /proc/1291/comm /proc/13/comm /proc/1318/comm /proc/13664/comm /proc/13684/comm /proc/13723/comm /proc/13742/comm /proc/13755/comm /proc/13775/comm /proc/138/comm /proc/13833/comm /proc/1385/comm /proc/13850/comm /proc/139/comm /proc/13919/comm /proc/13920/comm /proc/13926/comm /proc/140/comm /proc/1404/comm /proc/141/comm /proc/14126/comm /proc/14127/comm /proc/14128/comm /proc/142/comm /proc/14200/comm /proc/14217/comm /proc/143/comm /proc/144/comm /proc/14426/comm /proc/1444/comm /proc/145/comm /proc/146/comm /proc/1461/comm /proc/1467/comm /proc/1476/comm /proc/14800/comm /proc/1481/comm /proc/14820/comm /proc/14871/comm /proc/14889/comm /proc/15/comm /proc/150/comm /proc/1518/comm /proc/15279/comm /proc/15280/comm /proc/15281/comm /proc/15334/comm /proc/15335/comm /proc/15336/comm /proc/15337/comm /proc/15338/comm /proc/15339/comm /proc/15340/comm /proc/15341/comm /proc/15555/comm /proc/15935/comm /proc/15952/comm /proc/16/comm /proc/1621/comm /proc/1635/comm /proc/16385/comm /proc/164/comm /proc/16430/comm /proc/165/comm /proc/16649/comm /proc/16664/comm /proc/16679/comm /proc/16723/comm /proc/1694/comm /proc/1695/comm /proc/17/comm /proc/17124/comm /proc/17146/comm /proc/1721/comm /proc/17249/comm /proc/17256/comm /proc/17277/comm /proc/17281/comm /proc/17286/comm /proc/17303/comm /proc/17305/comm /proc/17330/comm /proc/17354/comm /proc/17375/comm /proc/17391/comm /proc/17397/comm /proc/17428/comm /proc/17438/comm /proc/17448/comm /proc/17456/comm /proc/17461/comm /proc/17462/comm /proc/17465/comm /proc/17466/comm /proc/17467/comm /proc/17468/comm /proc/17480/comm /proc/17488/comm /proc/17489/comm /proc/17493/comm /proc/17507/comm /proc/17520/comm /proc/17532/comm /proc/1757/comm /proc/1765/comm /proc/17872/comm /proc/18/comm /proc/18032/comm /proc/18056/comm /proc/18100/comm /proc/18127/comm /proc/18158/comm /proc/18301/comm /proc/18428/comm /proc/18444/comm /proc/18467/comm /proc/18471/comm /proc/18478/comm /proc/18505/comm /proc/18611/comm /proc/18634/comm /proc/18640/comm /proc/18665/comm /proc/18728/comm /proc/1905/comm /proc/1943/comm /proc/1944/comm /proc/1950/comm /proc/1966/comm /proc/19805/comm /proc/19808/comm /proc/19837/comm /proc/1987/comm /proc/19892/comm /proc/19897/comm /proc/19898/comm /proc/19899/comm /proc/19900/comm /proc/2/comm /proc/20/comm /proc/2004/comm /proc/2007/comm /proc/2008/comm /proc/20102/comm /proc/2020/comm /proc/2025/comm /proc/2036/comm /proc/20394/comm /proc/2040/comm /proc/2041/comm /proc/2045/comm /proc/2050/comm /proc/2052/comm /proc/20583/comm /proc/2059/comm /proc/2061/comm /proc/20610/comm /proc/2063/comm /proc/2068/comm /proc/2090/comm /proc/2095/comm /proc/20991/comm /proc/21/comm /proc/210/comm /proc/2100/comm /proc/2101/comm /proc/2102/comm /proc/21023/comm /proc/21068/comm /proc/21092/comm /proc/212/comm /proc/213/comm /proc/2132/comm /proc/214/comm /proc/21448/comm /proc/21449/comm /proc/2145/comm /proc/21450/comm /proc/21451/comm /proc/21459/comm /proc/215/comm /proc/2151/comm /proc/21526/comm /proc/21553/comm /proc/2156/comm /proc/216/comm /proc/2162/comm /proc/2167/comm /proc/21673/comm /proc/2169/comm /proc/217/comm /proc/218/comm /proc/2182/comm /proc/21886/comm /proc/219/comm /proc/21901/comm /proc/21911/comm /proc/21937/comm /proc/21938/comm /proc/21939/comm /proc/21940/comm /proc/2196/comm /proc/2197/comm /proc/2198/comm /proc/22/comm /proc/220/comm /proc/22050/comm /proc/221/comm /proc/22134/comm /proc/22158/comm /proc/22185/comm /proc/222/comm /proc/22218/comm /proc/223/comm /proc/224/comm /proc/22437/comm /proc/22459/comm /proc/22491/comm /proc/22568/comm /proc/22604/comm /proc/22707/comm /proc/22729/comm /proc/22742/comm /proc/22764/comm /proc/22771/comm /proc/22790/comm /proc/22795/comm /proc/22798/comm /proc/22800/comm /proc/22801/comm /proc/22802/comm /proc/22803/comm /proc/22843/comm /proc/22864/comm /proc/23/comm /proc/230/comm /proc/23011/comm /proc/23045/comm /proc/231/comm /proc/23100/comm /proc/2314/comm /proc/23176/comm /proc/232/comm /proc/23215/comm /proc/23262/comm /proc/23295/comm /proc/233/comm /proc/23305/comm /proc/23323/comm /proc/23364/comm /proc/23406/comm /proc/23421/comm /proc/23422/comm /proc/23423/comm /proc/23425/comm /proc/23426/comm /proc/23427/comm /proc/23430/comm /proc/23438/comm /proc/23439/comm /proc/23440/comm /proc/23441/comm /proc/23442/comm /proc/23443/comm /proc/23444/comm /proc/23445/comm /proc/23446/comm /proc/23447/comm /proc/23452/comm /proc/23462/comm /proc/23487/comm /proc/23525/comm /proc/23527/comm /proc/23532/comm /proc/23571/comm /proc/23575/comm /proc/23576/comm /proc/23579/comm /proc/23615/comm /proc/23618/comm /proc/23782/comm /proc/23802/comm /proc/23834/comm /proc/23835/comm /proc/239/comm /proc/240/comm /proc/24034/comm /proc/24061/comm /proc/24070/comm /proc/24079/comm /proc/241/comm /proc/24106/comm /proc/24107/comm /proc/24143/comm /proc/24173/comm /proc/24393/comm /proc/24419/comm /proc/24495/comm /proc/24522/comm /proc/24631/comm /proc/24637/comm /proc/24668/comm /proc/24671/comm /proc/24774/comm /proc/24803/comm /proc/24865/comm /proc/24889/comm /proc/24993/comm /proc/25/comm /proc/25016/comm /proc/25204/comm /proc/25240/comm /proc/25297/comm /proc/25298/comm /proc/25299/comm /proc/25300/comm /proc/25301/comm /proc/25302/comm /proc/25303/comm /proc/25304/comm /proc/25305/comm /proc/25306/comm /proc/25329/comm /proc/25372/comm /proc/25378/comm /proc/25424/comm /proc/25440/comm /proc/25463/comm /proc/257/comm /proc/25897/comm /proc/26/comm /proc/26093/comm /proc/26095/comm /proc/26200/comm /proc/26235/comm /proc/26334/comm /proc/26440/comm /proc/26467/comm /proc/26615/comm /proc/26635/comm /proc/2665/comm /proc/2666/comm /proc/2667/comm /proc/26835/comm /proc/26873/comm /proc/26879/comm /proc/26977/comm /proc/26978/comm /proc/27/comm /proc/27521/comm /proc/27522/comm /proc/27523/comm /proc/27524/comm /proc/27525/comm /proc/27526/comm /proc/27528/comm /proc/27529/comm /proc/27530/comm /proc/27538/comm /proc/27562/comm /proc/27591/comm /proc/27607/comm /proc/27644/comm /proc/27687/comm /proc/27734/comm /proc/28/comm /proc/2825/comm /proc/283/comm /proc/284/comm /proc/28480/comm /proc/2850/comm /proc/28521/comm /proc/28581/comm /proc/28738/comm /proc/28762/comm /proc/2929/comm /proc/29570/comm /proc/29616/comm /proc/29707/comm /proc/29708/comm /proc/29709/comm /proc/29852/comm /proc/29855/comm /proc/29875/comm /proc/29876/comm /proc/29890/comm /proc/29913/comm /proc/29916/comm /proc/29922/comm /proc/3/comm /proc/30/comm /proc/30020/comm /proc/30041/comm /proc/30076/comm /proc/30099/comm /proc/30121/comm /proc/30184/comm /proc/30185/comm /proc/30186/comm /proc/30187/comm /proc/30188/comm /proc/30189/comm /proc/30191/comm /proc/30255/comm /proc/30292/comm /proc/30354/comm /proc/30420/comm /proc/30446/comm /proc/30460/comm /proc/30490/comm /proc/30492/comm /proc/30520/comm /proc/30532/comm /proc/30544/comm /proc/30550/comm /proc/30670/comm /proc/30681/comm /proc/30703/comm /proc/30755/comm /proc/30852/comm /proc/30871/comm /proc/31/comm /proc/31139/comm /proc/31242/comm /proc/313/comm /proc/31401/comm /proc/31402/comm /proc/31570/comm /proc/31571/comm /proc/31572/comm /proc/3183/comm /proc/32/comm /proc/320/comm /proc/32086/comm /proc/32157/comm /proc/32158/comm /proc/32164/comm /proc/3229/comm /proc/32480/comm /proc/32482/comm /proc/32483/comm /proc/32484/comm /proc/32489/comm /proc/32490/comm /proc/32676/comm /proc/33/comm /proc/3461/comm /proc/35/comm /proc/36/comm /proc/37/comm /proc/373/comm /proc/38/comm /proc/381/comm /proc/3893/comm /proc/3901/comm /proc/391/comm /proc/40/comm /proc/4022/comm /proc/408/comm /proc/41/comm /proc/4122/comm /proc/4123/comm /proc/4190/comm /proc/4192/comm /proc/4193/comm /proc/4195/comm /proc/42/comm /proc/4203/comm /proc/4204/comm /proc/4205/comm /proc/4206/comm /proc/4271/comm /proc/43/comm /proc/4317/comm /proc/4330/comm /proc/45/comm /proc/46/comm /proc/47/comm /proc/4715/comm /proc/48/comm /proc/4872/comm /proc/497/comm /proc/4976/comm /proc/5/comm /proc/50/comm /proc/5002/comm /proc/504/comm /proc/5040/comm /proc/505/comm /proc/5063/comm /proc/51/comm /proc/52/comm /proc/5232/comm /proc/525/comm /proc/5260/comm /proc/53/comm /proc/5307/comm /proc/5325/comm /proc/5347/comm /proc/544/comm /proc/55/comm /proc/56/comm /proc/5688/comm /proc/57/comm /proc/5711/comm /proc/58/comm /proc/5904/comm /proc/5928/comm /proc/5939/comm /proc/5977/comm /proc/5986/comm /proc/60/comm /proc/6087/comm /proc/61/comm /proc/62/comm /proc/6276/comm /proc/63/comm /proc/649/comm /proc/65/comm /proc/6545/comm /proc/66/comm /proc/668/comm /proc/669/comm /proc/67/comm /proc/670/comm /proc/671/comm /proc/672/comm /proc/674/comm /proc/68/comm /proc/6811/comm /proc/7/comm /proc/70/comm /proc/71/comm /proc/72/comm /proc/7272/comm /proc/7273/comm /proc/73/comm /proc/7341/comm /proc/7394/comm /proc/7432/comm /proc/7455/comm /proc/7478/comm /proc/7479/comm /proc/7480/comm /proc/7481/comm /proc/75/comm /proc/76/comm /proc/7661/comm /proc/7679/comm /proc/77/comm /proc/7707/comm /proc/78/comm /proc/785/comm /proc/8/comm /proc/80/comm /proc/8015/comm /proc/8035/comm /proc/8064/comm /proc/81/comm /proc/8108/comm /proc/8125/comm /proc/8126/comm /proc/82/comm /proc/83/comm /proc/840/comm /proc/85/comm /proc/851/comm /proc/855/comm /proc/86/comm /proc/860/comm /proc/862/comm /proc/87/comm /proc/8799/comm /proc/88/comm /proc/8829/comm /proc/8866/comm /proc/89/comm /proc/893/comm /proc/894/comm /proc/899/comm /proc/8996/comm /proc/9/comm /proc/90/comm /proc/91/comm /proc/912/comm /proc/913/comm /proc/916/comm /proc/92/comm /proc/922/comm /proc/93/comm /proc/94/comm /proc/948/comm /proc/95/comm /proc/9520/comm /proc/9546/comm /proc/96/comm /proc/976/comm /proc/98/comm /proc/980/comm /proc/9876/comm /proc/988/comm /proc/99/comm /proc/9901/comm /proc/self/comm /proc/thread-self/comm
+ '[' -n '' ']'
+ rm -f /var/run/libvirtd.pid
+ [[ -c /dev/kvm ]]
+ chmod 660 /dev/kvm
+ chown root:kvm /dev/kvm
+ '[' -d /sys/kernel/mm/hugepages ']'
++ grep KVM_HUGEPAGES=0 /etc/default/qemu-kvm
+ '[' -n KVM_HUGEPAGES=0 ']'
+ sed -i 's/.*KVM_HUGEPAGES=0.*/KVM_HUGEPAGES=1/g' /etc/default/qemu-kvm
+ '[' -n 457eb676-33da-42ec-9a8c-9293d545c337 ']'
+ libvirtd --listen
++ mktemp --suffix .xml
libvirtd: error while loading shared libraries: libvirt-admin.so.0: cannot stat shared object: Permission denied
+ tmpsecret=/tmp/tmp.KpCgmWAeTV.xml
+ trap cleanup EXIT
+ TIMEOUT=60
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 60 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 59 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 58 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 57 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 56 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 55 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 54 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 53 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 52 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 51 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 50 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 49 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 48 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 47 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 46 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 45 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 44 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 43 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 42 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 41 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 40 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 39 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 38 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 37 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 36 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 35 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 34 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 33 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 32 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 31 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 30 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 29 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 28 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 27 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 26 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 25 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 24 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 23 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 22 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 21 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 20 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 19 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 18 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 17 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 16 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 15 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 14 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 13 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 12 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 11 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 10 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 9 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 8 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 7 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 6 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 5 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 4 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 3 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 2 -gt 0 ]]
+ let TIMEOUT-=1
+ sleep 1
+ [[ ! -f /var/run/libvirtd.pid ]]
+ [[ 1 -gt 0 ]]
+ let TIMEOUT-=1
+ cleanup
+ rm -f /tmp/tmp.KpCgmWAeTV.xml
