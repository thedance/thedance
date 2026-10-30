# Idols - Oracle VPS for VPNs
Always free `VPN` using oracle `VPS`

Oracle Offers always free Virtual Private Servers Instance, either AMD or ARM, making it perfect for usage as as server, or in this case, as a `VPN`, and it's quite easy to set it up

## Getting Started 

Your billing information must be accurate, the billing country is the country you live, later on they ask to insert where the instance is actually located, I have multiple accounts, you need to use a different email for each
https://signup.cloud.oracle.com/

There's some good guides around, I wont explain the whole process to create an account

They ask for your credit card, but the whole thing is free
### Creating an Instance

https://www.oracle.com/cloud/sign-in.html
Sign in on this website, they ask for you username instead of email what's not very clear

Search for Instances
![[Pasted image 20261030140202.png]]

Create an Instance
![[Pasted image 20261030140317.png]]

Make Sure to use `Ubuntu 24.04` as the Image, and the `1 core 1 GB AMD` shape that is always free eligible, you can change based on your preferences, I find this set easier to use
Notice also in the upper right corner shows the region where your account was created, **it cannot be changed**, the `VPN` will have this location

![[Pasted image 20261030140405.png]]


Don't bother about the `Estimated cost` it's fake, freeze your card if you're a fearful broke student like me
Create a `new virtual cloud network` and `new public subnet` if you don't already have one

Skip everything and download your `SSH keys`
![[Pasted image 20261030141221.png]]

Go next next until it's done

### Assign a Public IP

We'll need a public `IP` to connect to the instance using `ssh` and to use as our `exit node` later on
Click on your `Instance`, go to `Networking` and scroll to `Attached VNICs`
Click on the dots and `View details`

![[Pasted image 20261030141825.png]]

Go to IP `administration` and `Edit`

![[Pasted image 20261030142521.png]]

`Create new Reserved IP Name`
My IP got blacklisted my Netflix sometimes, I just created a new Reserved IP, it's free
If it happens and you create more than one IP just use the search bar to look for `Reserved public IPs` and terminate the ones that are not assigned 

![[Pasted image 20261030142702.png]]

**DONE** we can close this hellish GUI now and go to the terminal, get your public IP address 
and ssh keys

## Terminal

``` code
ssh -i <ssh-key> ubuntu@<public-ip>
```

...
# Reference | 参考