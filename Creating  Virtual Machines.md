# Lab: Creating Virtual Machines

The objectives in this lab include:
   1. Create several standard VMs
   2. Create advanced VMs

# Steps
1. Create a utility virtual machine
   - gcloud compute instances create utility-vm --zone=us-central1-c --machine-type=n1-standard-1 --subnet=default --image=debian-10-buster-v20200902 --image-project=debian-cloud 

2. Create a Windows virtual machine
   - gcloud beta compute create windows-vm --zone=europe-west2-a --machine-type=n1-standard-2 --subnet=default --tags=http-server,https-server --image=windows-server-2016-dc-core-v20200813 --image-project=windows-cloud --boot-disk-size=100GB --boot-disk-type=pd-ssd --boot-disk-device-name=windows-vm

   - gcloud compute firewall-rules create default-allow-http --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server
   
   - gcloud compute firewall-rules create default-allow-https --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:443 --source-ranges=0.0.0.0/0 --target-tags=https-server
   
3. Create a custom virtual machine
   - gcloud beta compute instances create custom-vm --zone=us-west1-b --machine-type=e2-custom-6-32768 --subnet=default --image=debian-10-buster-v20200902 --image-project=debian-cloud --boot-disk-size=10GB --boot-disk-type=pd-standard --boot-disk-device-name=custom-vm 
 
 To explore the newly created VM, one can run the following commands:
   - free                  # To see information about unused and used memory and swap space on your custom VM
   - sudo dmidecode -t 17  # To see he RAM of the machine
   - nproc                 # To view the number of processors
   - lscpu                 # To see details about the CPUs installed on your VM
