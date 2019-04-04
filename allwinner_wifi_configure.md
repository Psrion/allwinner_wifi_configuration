

While received wifi configuration of wifi name and passwd,just do as follow:

	step: First received wifi configuration account number

		netcfg  wlan0 down
		netcfg  wlan0 up
		wpa_cli -iwlan0 scan
		wpa_cli -iwlan0 scan_results
		wpa_cli -iwlan0 add_network
		wpa_cli -iwlan0 add_network
		wpa_cli -iwlan0 set_network 1 ssid '"weiding_v3s"'
		wpa_cli -iwlan0 set_network 1 key_mgmt WPA-PSK
		wpa_cli -iwlan0 set_network 1 psk '"v3sv3s2018"'
		wpa_cli -iwlan0 select_network 1
		dhcpcd wlan0

		#omit  start
		netcfg  wlan0 down
		netcfg  wlan0 up
		wpa_cli -iwlan0 scan
		wpa_cli -iwlan0 scan_results
		wpa_cli -iwlan0 set_network 1 ssid '"weiding_v3s"'
		wpa_cli -iwlan0 set_network 1 key_mgmt WPA-PSK
		wpa_cli -iwlan0 set_network 1 psk '"v3sv3s2018"'
		wpa_cli -iwlan0 select_network 1

		netcfg  wlan0 down
		netcfg  wlan0 up
		wpa_cli -iwlan0 scan
		wpa_cli -iwlan0 scan_results
		wpa_cli -iwlan0 set_network 1 ssid '"yoko"'
		wpa_cli -iwlan0 set_network 1 key_mgmt WPA-PSK
		wpa_cli -iwlan0 set_network 1 psk '"zzj123456"'
		wpa_cli -iwlan0 select_network 1

		#omit end


	step 2: judge whether ssid is exist

		iwconfig wlan0  



	step 3: configure anothread account number

		netcfg  wlan0 down
		netcfg  wlan0 up
		wpa_cli -iwlan0 select_network 1





	Notice: when it has another account number, just do as follow: 

	original: 
		netcfg  wlan0 up
		wpa_cli -iwlan0 scan
		wpa_cli -iwlan0 scan_results

		wpa_cli -iwlan0 set_network 1 ssid '"weiding_v3sccc"'
		wpa_cli -iwlan0 set_network 1 key_mgmt WPA-PSK
		wpa_cli -iwlan0 set_network 1 psk '"v3sv3s2018"'
		wpa_cli -iwlan0 select_network 1

	just now: 

		wpa_cli -iwlan0 add_network
		wpa_cli -iwlan0 set_network 1 ssid '"yoko"'
		wpa_cli -iwlan0 set_network 1 key_mgmt WPA-PSK
		wpa_cli -iwlan0 set_network 1 psk '"zzj123456"'
		wpa_cli -iwlan0 select_network 1



