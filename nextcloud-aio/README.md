Log in using your Nextcloud AIO password:
 $sudo cat /var/lib/docker/volumes/nextcloud_aio_mastercontainer/_data/data/configuration.json | grep password






#Posibles errores:
 ## Caddy warning failed to sufficiently increase receive buffer size
	Solution
echo "net.core.rmem_max = 2500000" | sudo tee /etc/sysctl.d/nextcloud-aio-buffer-increase.conf should be set, to increase buffer size on reboot, change will apply after reboot or see the line below how to activate it temporary without reboot
sysctl "net.core.rmem_max=2500000" enables buffer size increase on-the-fly temporary, then restart Nextcloud AIO from the AIO Interface

