# Configruing the repositories in the Linux

For RHCSA exam they will give you the the URL for which you need to configure the repo for that you need to follow few steps

1. Switch to Root user if not and check whether the file name exist in the folder named /etc/yum.repo.d. You can create a new file named as local.repo
2. Add 4 entry for each url. Lets says if you have two baseurl u need to make in total of 8 entry. The entries are as follows:
>name=anyname_you_wany
>
>baseurl=your_url
>
>gpgcheck = 0
>
>enabled = 1

#### Note - The package manager for Centos is yum. If you want to install any package you need to write yum install package_name. Package manager is different for different OS. While running yum install make sure either you are installing the package as a root user or you have sudo permission enabled on your account.
