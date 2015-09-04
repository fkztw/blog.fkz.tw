Title: Install Arch Linux on MacBook Air Mid 2013  
Slug: install-arch-linux-on-macbook-air-mid-2013  
Date: 2015-08-19 14:08:04  
Authors: m157q  
Category: Note  
Tags: Arch Linux, MacBook Air, Linux  
Modified: 2015-08-27 02:55:40  
Summary: 參加完 COSCUP 2015，聽完 jserv 的封麥演說以及一句「Linux 使用者有錢以後就會投入 Mac 的懷抱」覺得自己深深中槍，備感慚愧。於是決定來做一件很久以前其實就想做的事：跟 Linus Torvalds 一樣，把 MacBook Air 上的 OS X 砍了，直接灌 Linux 來用。當然，Arch Linux 是首選。以下紀錄一下過程，給有需要的人參考。  
  
---  
  
> 使用上遇到問題，才有動力去解決、改善、貢獻並回饋程式碼到上游。  
  
> 警告: 把 OS X 砍掉的話，之後要更新 firmware 必須使用有安裝 OS X 的外接硬碟上開機才能更新。  
  
  
改用 OS X 的這兩年，也不是說就完全沒用 Linux 了，舊的筆電退役成 Server 架在宿舍裡，  
一個不用桌面環境的 Linux ，使用起來基本上是不會遇到太多問題的。  
而 OS X 的確遇到使用上的問題減少了。  
用起來的確跟當初想的一樣，是個問題比較沒那麼多的 UNIX-like System  
但同時也在不知不覺中漸漸喪失了解決問題的能力，  
就好像一把兩年前就不再磨的刀劍，愈發鈍鏽。  
當初會買 MacBook Air 而不選擇 UltraBook 的原因主要是因為價錢、續航力、重量都是 MacBook Air 勝出，  
當然之後在使用上，我也對重量和續航力很滿意，  
但其實在使用 OS X 上也遇過許多無法接受的問題，有些妥協了，有些沒有  
例如：  
+ 原生的工具都非常老舊，舊版本代表著很多問題，無論是資安或是有無新功能。這對於一個從使用 Rolling Release 的 Arch Linux user 來說真的很不習慣。  
    + 骨灰級的 Bash 真的令我印象深刻，如果沒有 Homebrew 的話，我肯定無法用這麼久，感謝 @mxcl  
+ 接網路線跟螢幕線得額外花錢買轉接頭  
    + 兩個加起來新台幣 1,600 左右。恩，我跟很多人一樣都買了。  
+ OS X 10.9 以前的視窗放大真的很雞肋和令人哭笑不得，放大後不會佔滿整個桌面，有時候甚至比按完放大前更小。  
    + 在 OS X 10.10 後，放大功能直接改成全螢幕了。恩，不意外，我在 10.9 以前早就都用全螢幕了。  
+ 雙螢幕在 OS X 10.10 仍然有一個我常常踩到的詭異Bug，如果有程式被丟到外接螢幕那邊，在不拔掉螢幕線的情況下，把螢幕闔上進入休眠，接著把螢幕線拔掉，然後喚醒 Mac，這時候就會發現被丟到外接螢幕的應用程式仍然被認為是在外接螢幕的範圍但因為早就沒有外接螢幕了，所以即便程式仍然在執行，使用者也根本看不到畫面，重點是重新執行該程式也無法解決這問題，只能登出、重開機或是重新接上外接螢幕在電腦喚醒的情況下拔掉螢幕線，或是把該程式拉回原生螢幕，才有辦法解決。  
    + 我不確定 Reproduce 的機率是不是 100%，寫這篇文章的時候已經把 OS X 砍了，所以也無從驗證。  
+ 系統介面內建中文字型不好看，要改也很難改。  
    + 還好 OS X 10.9 以前有 TCFail 能用，到了 OS X 10.10 只能去改系統檔案設定，而換成了我想用的字型以後，內建的中文輸入法就會掛掉，只好又改回原本的字型。  
+ 輸入法也是個問題  
    + 剛用 OS X 10.8 的時候就聽很多人說內建的中文輸入法不是很好用，所以很多人都裝開源的香草或是小麥注音，我本身也是注音輸入法的使用者，但我用了以後還是不太習慣(恩，當時明明用不習慣，卻沒有跳下去開發)。後來找到另一款開源的中州韻輸入法(RIME)，是對岸的中國人[佛振](https://github.com/lotem)開發的，在 Windows, Linux, Mac 上都能使用。裝來用以後發現還不錯用，自訂性蠻強大的，由於在用 gcin 時，我習慣把選字鍵從常人慣用的 1234567890 改成 asdfghjkl; 以減少手指移動的距離，這款輸入法也能做到，於是就用了。(至於後來關於 dvorak 跟拼音輸入法又是另一個故事了)  
    + 到了 OS X 10.10 之後，不知怎的，非官方的中文輸入法都變得超級慢，慢到無法接受，於是又換回不是很好用的官方中文輸入法。(恩，又是一個妥協，沒去追根究底找出為什麼變得這麼慢的原因)  
  
一不小心好像離題寫了太多關於 OS X 的部份。  
Anyway, 因為種種問題加上這次 COSCUP 的助力，還是想回歸到 Linux 的懷抱，促使我把 Arch Linux 灌在 Mac 上，以下是紀錄。  
  
---  
  
以下環境為 MacBookAir6,2 (Macbook Air mid 2013)  
不同 model 的 MacBook 會有不同的問題  
詳見 <https://wiki.archlinux.org/index.php/MacBook#Model-specific_information>  
由於我是採用把 OS X 洗掉直接裝 Arch Linux 的方式，並不是雙系統  
所以安裝方式與一般的 Arch Linux 安裝並無太大不同，  
故本篇文章會著重在裝好之後的一些調整  
  
如果有人想灌成 Ubuntu 的話，可以參考 <https://help.ubuntu.com/community/MacBookAir>  
(但上面最新的資料似乎只有到 2013 年的機種就是，當然也歡迎勇者測試之後貢獻)  
  
> 警告：MacbookAir6,2 的網卡在 Linux 上"有可能"不被支援(需視網卡型號)，  
> 所以可能得另購 USB 無線網卡才有無線網路  
> 詳情請見底下關於 Wi-Fi 的部份  
  
  
# Install Arch Linux Only (No OS X Dual Boot) on MacBook Air  
  
> WARNING: After erasing OS X, We can only update the MacBook Air firmware via the external drive which has already installed OS X.  
  
1. Make Arch Linux bootable Live USB  
    + Go to <https://www.archlinux.org/download/> and download the newest Arch Linux iso.  
    + Plug in a USB drive  
    + use `diskutil list` to find the USB dirve `/dev/sdX`  
    + `dd if=$(path to arch linux iso) of=/dev/rsdX bs=1m`  
        + use raw disk (/dev/rsdX) make this quicker.  
2. Go to AppStore for updating OS X to the newest version  
    + After the first update, reboot, and check for newest update again  
    + Make sure it's newest update, espcially the firmware udpate  
3. Erase OS X  
    + Reboot MacBook Air  
    + Press Command + R to enter the Reinstall mode  
    + Choose DiskUtility and Erase the entire disk  
4. Entering Arch Linux Live USB installation  
    + Reboot MacBook Air  
    + Press alt/option key for entering EFI bootloader  
    + Choose EFI USB  
5. Install Arch Linux (Just like the normal installation with a little different)  
    + [Beginners' guide - ArchWiki](https://wiki.archlinux.org/index.php/Beginners'_guide)  
    + Important => [MacBook - ArchWiki](https://wiki.archlinux.org/index.php/MacBook#Arch_Only_Installation)  
    + Need to be aware about the EFI related options  
  
---  
  
> 底下其實有些調整不是那麼必要  
> 可能直接 `sudo pacman -S gnome-control-center` 就可以解掉許多問題  
> 只是個人覺得 gnome 太肥，想要用些 light weight 的 packages  
> 覺得麻煩的人可以直接裝 gnome 的東西，然後再視情況安裝需要的東西  
> 應該可以節省一些時間  
  
# Post-Install  
+ <https://wiki.archlinux.org/index.php/MacBook#Post-installation>  
+ <https://wiki.archlinux.org/index.php/General_recommendations>  
+ Install [yaourt](https://aur.archlinux.org/packages/yaourt/)  
    + `sudo mkdir /var/cache/yaourt`  
    + save tarball to /var/cache/yaourt  
```  
/etc/yaourtrc  
---  
EXPORT=1  
EXPORTDIR="/var/cache/yaourt"  
```  
  
  
## Configs  
### dotfiles  
Download my dot files on <https://github.com/M157q/rcfiles>  
```sh  
git clone https://github.com/M157q/rcfiles  
cd rcfiles  
make install  
```  
  
  
### Disable Mac Boot Sound  
  
### Prevent shutdown directly when power button is pressed  
  
### Xorg  
+ `sudo pacman -S xcompmgr xorg-xrdb`  
    + [xcommpgr](https://wiki.archlinux.org/index.php/Xcompmgr) for simple effect like transparency of guake  
    + [xorg-xrdb](https://wiki.archlinux.org/index.php/X_resources) for .Xresources, some config related to X Window  
  
  
### Wi-Fi  
不同型號的網卡會有不同的問題，這部份也需要多加注意。  
光是參考 <https://wiki.archlinux.org/index.php/MacBook#Wi-Fi> 可能不夠  
必須再自行找些相關資料，我在這部份卡了一陣子。  
  
先確認是哪張網卡  
MacBookAir6,2 沒意外的話應該都是 BCM4360 這張  
但還是有細節得注意  
  
```  
$ lspci -vnn |grep 0280  
03:00.0 Network controller [0280]: Broadcom Corporation BCM4360 802.11ac Wireless Network Adapter [14e4:43a0] (rev 03)  
```  
  
Broadcom BCM4360 這張網卡有兩種  
一種是 14e4:43a0, 另外一種是 14e4:4360  
根據 <https://wireless.wiki.kernel.org/en/users/Drivers/b43?highlight=%28b43%29#Supported_devices>  
43a0 這張是被 wl 驅動程式支援的，所以如果是這張的話可以用無線網路  
4360 這張則是不被支援的，所以可能需要另外購買無線網卡  
(我沒有親自測試過，如果有勇者或是有經驗的人歡迎回覆告知)  
  
43a0 的話照著底下的指令做應該就可以使用無線網路連網了 (kerel 為 Linux 4.1.5-1)  
+ `yaourt -S broadcom-wl-dkms`  # follow the postinstall instructions  
+ `sudo pacman -S iw`  
+ `sudo pacman -S wicd-gtk`  
```  
==> You need to restart the dbus service after  
==> upgrading wicd.  
==> Disable networkmanager, dhcpcd or other networking  
==> utility and add 'wicd' to your systemd configuration.  
```  
> 記得 disable dhcpcd 然後 enable wicd，  
> dhcpcd 跟 wicd 會衝突，開著 dhcpcd 的時候使用 wicd 的話  
> 會無法使用無線網路連線，錯誤訊息也看不出啥端倪，我就是卡在這很久Orz  
  
### File Manager  
+ `sudo pacman -S pcmanfm`  
  
  
### Keyboard  
+ `sudo pacman -S xorg-xmodmap`  #for changing keymap like swap Ctrl and Caps Lock  
+ Check /etc/mkinitcpio.conf if `HOOKS` have `keyboard`, if not, add it then `sudo mkinitcpio -p linux`  
+ fix '~' problem  
```  
/etc/modprobe.d/hid_apple.conf  
---  
options hid_apple iso_layout=0  
```  
  
#### Backlight  
+ <https://wiki.archlinux.org/index.php/MacBook#Keyboard_Backlight>  
+ `yaourt -S kbdlight`  
+ `sudo pacman -S sxhkd`  
    + use sxhkd to combine hotkey for kbdlight  
    + <https://wiki.archlinux.org/index.php/Sxhkd>  
+ `sudo pacman -S xorg-xev`  
    + For chekcing the key value of keyboard  
  
#### Function keys  
+ <https://wiki.archlinux.org/index.php/Sxhkd>  
> to be continued...  
  
  
### Synaptic (Touchpad)  
+ `sudo pacman -S xf86-input-synaptics`  # only basic functions  
or  
+ `yaourt xf86-input-mtrack-git`  #for OS X like touchpad and flexible configuration  
```  
/usr/share/X11/xorg.conf.d/10-mtrack.conf  
---  
Section "InputClass"  
    MatchIsTouchpad "on"  
    Identifier "Touchpads"  
    Driver "mtrack"  
  
    Option "Thumbsize" "50"  
    Option "ScrollDistance" "100"  
  
    # Natural Scrolling  
    Option "ScrollUpButton" "5"  
    Option "ScrollDownButton" "4"  
    Option "ScrollLeftButton" "7"  
    Option "ScrollRightButton" "6"  
EndSection  
```  
  
### Bluetooth (Headset)  
+ links  
    + <https://wiki.archlinux.org/index.php/Bluetooth>  
    + <https://wiki.archlinux.org/index.php/Blueman>  
    + <https://wiki.archlinux.org/index.php/Bluetooth_headset>  
+ `sudo pacman -S bluez bluez-utils bluez-libs bluez-firmware blueman pulseaudio-bluetooth pulseaudio-alsa pavucontrol`  
+ `sudo modprobe btusb`  
+ `sudo systemctl enable bluetooth`  
+ `sudo systemctl start bluetooth`  
+ `blueman-manager`  
    + scan, pair, connect  
+ `pavucontrol`  
    + Change sound channel to bluetooth headset  
  
  
  
### Sound  
+ `sudo pacman -S xf86-video-intel alsa-utils`  
    + alsa-utils include alsamixer, amixer  
+ Add the content below to `/etc/asound.conf` //Important  
    + `/etc/asound.conf` should be created after installed `pulseaudio-alsa`  
```  
/etc/asound.conf  
---  
defaults.pcm.card 1  
defaults.pcm.device 0  
defaults.ctl.card 1  
```  
  
  
### awesomewm  
+ `sudo pacman -S awesome vicious`  
+ `cp -r /usr/share/awesome/themes ~/.config/awesome/`  
  
  
### Power Management  
+ <https://wiki.archlinux.org/index.php/Power_management>  
+ `sudo pacman -S acpi powertop tlp`  
+ powertop  
    + `sudo powertop --auto-tune`  
> to be continued...  
  
### Monitor  
#### Dual Display  
+ <https://wiki.archlinux.org/index.php/Multihead>  
+ `sudo pacman -S xorg-xrandr`  
    + <https://wiki.archlinux.org/index.php/Xrandr>  
    + xrandr should work.  
        + But my 1280x720 external display only get 1024x768 support  
        + Maybe the problem is on the offical thunderbolt2VGA adapter?  
+ For more friendly setting, `sudo pacman -S lxrandr`  
  
#### Birghtness  
+ `sudo pacman -S xorg-xbacklight`  
+ `yaourt -S mba6x_bl-dkms`  
+ (optional) `yaourt -S lightum-git`  
    + For auto adjust keyboard and monitor birghtness by light sensor  
    + The AUR version has bug, use this fork version <https://github.com/esoleyman/lightum>  
  
### USB  
+ `yaourt -S pmount`  
  
  
### Chinese  
  
#### IME  
+ `sudo pacman -S gcin`  
+ `sudo pacman -S libchewing`  # for chewing input method  
+ `sudo pacman -S anthy`  # for Japanese input method  
+ `sudo gtk-query-immodules-2.0 --update-cache`  
  
#### Browser  
+ `sudo pacman -S firefox firefox-i18n-zh-tw`  
+ Flash  
    + `sudo pacman -S flashplugin`  
    + <https://addons.mozilla.org/en-US/firefox/addon/flashblock/>  
  
#### Fonts  
+ `sudo pacman -S wqy-zenhei adobe-source-han-sans-tw-fonts`  
  
### Mobile  
#### USB-Tethering (Works out of box)  
+ <https://wiki.archlinux.org/index.php/Android_tethering#USB_tethering>  
#### Mount Android phone  
+  
  
  
---  
  
There are my personal needed below. It's optional.  
<https://wiki.archlinux.org/index.php/List_of_applications>  
  
## Misc  
+ `sudo pacman -S virtualbox`  
+ `sudo pacman -S unrar`  
  
  
### Network  
+ `sudo pacman -S mosh mtr wget nmap`  
+ `sudo pacman -S dns-tools`   # for dig  
  
  
### Google Drive  
  
  
### Python  
+ `sudo pacman -S python2 python-pip`  
+ `sudo pip install virtualenvwrapper`  
  
#### Pelican  
+ `pip2 install pelican markdown ghp-impor`  
  
  
### GitHub  
+ Add SSH Key  
    + <https://help.github.com/articles/generating-ssh-keys/#platform-linux>  
  
  
### Screenshot  
+ `sudo pacman -S shutter`  
  
  
### Terminal  
+ `sudo pacman -S rxvt-unicode guake`  
  
  
### Monitoring  
+ `sudo pacman -S htop glances lm_sensors`  
    + `sudo sensors-detect`  
  
  
### Multi-Media  
+ `sudo pacman -S eog`  
+ `sudo pacman -S vlc`  
+ `yaourt -S wine-git`  
    + need to uncomment multilib in /etc/pacman.conf first  
+ `sudo pacman -S playonlinux`  
  
  
### Office  
+ `sudo pacman -S evince`   #for pdf  
+ `sudo pacman -S libreoffice`  
  
  
## App  
  
+ TweetDeck  
    + `yaourt -S nwjs-bin`  
    + <https://github.com/passcod/twd>  
        + `git clone https://github.com/passcod/twd.git`  
        + `cd twd`  
        + `nw .`  
        + Still buggy and need package on AUR  
+ Slack  
    + <https://github.com/raelgc/scudcloud>  
    + `yaourt -S scudcloud`  
+ Gitter  
    + `yaourt -S gitter`  
+ Facebook Messenger  
    + `yaourt -S messengerfordesktop`  
+ Popcorn-Time  
    + `yaourt -S popcorntime`  
    + Need some modifications about sha256sum and \_gitname  
  
---  
  
# References  
+ [MacBook - ArchWiki](https://wiki.archlinux.org/index.php/MacBook)  
    + Arch Linux Only, Dual Boot, Arch Linux + OS X + Windows  
+ [pandeiro/arch-on-air · GitHub](https://github.com/pandeiro/arch-on-air)  
    + Dual Boot  
+ [Mandriva: gcin 無法使用於 firefox, stardic](http://mandriva-usher.blogspot.tw/2014/02/gcin-firefox-stardic.html)  
+ [General recommendations - ArchWiki](https://wiki.archlinux.org/index.php/General_recommendations)  
+ [Beginners' guide - ArchWiki](https://wiki.archlinux.org/index.php/Beginners'_guide)  
+ [xf86-input-mtrack/README.md at master · BlueDragonX/xf86-input-mtrack · GitHub](https://github.com/BlueDragonX/xf86-input-mtrack/blob/master/README.md)  
+ [MacBook - ArchWiki](https://wiki.archlinux.org/index.php/MacBook#Mid_2013_13.22_-_Version_6.2C2)  
+ [List of applications - ArchWiki](https://wiki.archlinux.org/index.php/List_of_applications)  
+ [MacBookAir6-2/Trusty - Community Help Wiki](https://help.ubuntu.com/community/MacBookAir6-2/Trusty)  
+ [Apple Keyboard - ArchWiki](https://wiki.archlinux.org/index.php/Apple_Keyboard)  
+ [Sxhkd - ArchWiki](https://wiki.archlinux.org/index.php/Sxhkd)  
+ [Bluetooth - ArchWiki](https://wiki.archlinux.org/index.php/Bluetooth)  
+ [Bluetooth headset - ArchWiki](https://wiki.archlinux.org/index.php/Bluetooth_headset)  