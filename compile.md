Followed instructions in [this](https://www.cyberciti.biz/tips/compiling-linux-kernel-module.html) page to get the kernel object. 

## These are the things we have to address: 

1. All the nla-policy variables are not declared anywhere - it is the same in pie.c also. Should find out how it is working. 

2. Should checkout what that .type is. It is some structure's member. 

3. Error: 

/home/adwi/ALL/sem6/ACN/getobj/pi.c:229:28: error: ‘struct pi_vars’ has no member named ‘qlen’
  q->vars.qlen_old = q->vars.qlen;

4. Should **checkout struct tc_pie_xstats**. 

* **struct tc_pie_xstats** is present in **inclulde/uapi/linux/pkt_sched.h** .

* This structure is present for every AQM Algorithm. 

* So, we have to add this structure for PI also. 
