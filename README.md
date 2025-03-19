# windows-exporter-dashboard
Windows Exporter Dashboard
[in grafana dashboards](https://grafana.com/grafana/dashboards/14694)

# If You've installed windows_exporter already

* Open up `Control Panel` and uninstall `windows_exporter` from `Programs and Features`
 
# Usage
To use this dashboard you must install windows_exporter from [here](https://github.com/prometheus-community/windows_exporter) and after that you do not have to do any other thing. Dashboard will show what you saw in snapshots.

### How you can install windows_exporter to collect data for this dashboard:
* Download latest version of windows_exporter from [here](https://github.com/prometheus-community/windows_exporter/releases) (download `.msi` file)
* Open up a command prompt with administrator privileges (`Run as administrator`)
* Change directory to the location where you've downloaded the `.msi` installer
* Run below command :
```
msiexec /i windows_exporter-*-amd64.msi ENABLED_COLLECTORS="ad,adfs,cache,cpu,cpu_info,container,dfsr,dhcp,dns,fsrmquota,iis,logical_disk,logon,memory,msmq,mssql,netframework_clrexceptions,netframework_clrinterop,netframework_clrjit,netframework_clrloading,netframework_clrlocksandthreads,netframework_clrmemory,netframework_clrremoting,netframework_clrsecurity,net,process,remote_fx,service,tcp,time,vmware" TEXTFILE_DIR="C:\custom_metrics" LISTEN_PORT="9100"
```

* Add your VM into your Prometheus server (`prometheus.yml` file)

---
_**You can choose what to collect with `ENABLED_COLLECTORS` option. to learn more about collectors, look at windows_exporter github page [here](https://github.com/prometheus-community/windows_exporter)**_

