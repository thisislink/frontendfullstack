# Frontend Full Stack

Repo of files and projects created from going through Jem Young's Frontend Masters Full Stack for Front-End Engineers course.

## What is Full Stack Engineering

Full Stack engineering is having the ability to build an application from start to finish.

This means creating both the frontend and backend of an application.

## Command Line

The Command Line is an application which accepts specific instructions that allow you to interact with the computer you are using and servers that do not have a graphical user interface (GUI).

### Common Command Line Commands

| Command | Command Description                       |
| ------- | ----------------------------------------- |
| cd      | change directory                          |
| ls      | list directory contents                   |
| pwd     | print working (display current) directory |
| mkdir   | make directory                            |
| rmdir   | remove directory                          |
| cat     | show file contents                        |
| man     | command manual                            |
| less    | show file contents by page                |
| rm      | remove file                               |
| echo    | repeat input                              |

#### Specific Useful Commands I Use

| Command             | Command Description                                                                                    |
| ------------------- | ------------------------------------------------------------------------------------------------------ |
| rm -r directoryName | delete directory and all files within the directory                                                    |
| ls -al              | display all files and directories, including hidden files and directories within the current directory |
| clear               | clear Command Line screen                                                                              |
| cd ..               | move up a directory                                                                                    |

## What is a Shell?

A shell is a interpreter that takes commands (instructions), interprets the instructions so the system can understand the instructions provided. An example shell is bash.

## What is a Terminal?

The terminal runs shell applications and is just a wrapper.

An example terminal on Windows is Powershell.

## How Does the Internet Work?

When people interact with applications and browsers, requests and repsonses are made to and from globally public interconnected devices.

All of the connections that happen, happen through a series of wires and tubes that are connected across large bodies of water to make the conenctions possible globally.

## IP Addresses and Protocols

IP is the internet proctol that was and is the agreement made that says IP addresses are how computers and devices will communicate with each other.

### IP Address

An IP address is an address, similar to the address where you live.

#### IPV4 and IPV6

Both IPV4 and IPV6 are internet protocols that set the IP address standards.

IPV4 is a 32-bit address denoted as X.X.X.X where each X can be a number between 0 and 255.

IPV6 is a 128-bit address and can denoted as XXXX:XXXX:XXXX:XXXX.

## TCP and UDP

TCP - Transmission Control Protocol

UDP - User Datagram Protocol

TCP is lossless, meaning it is guaranteed that if data is sent over TCP, it will be received.

UDP will send data, but it does not care if there is any acknowledgement of the data being received.

UDP is faster, because it does not wait for any responses to connect or that data was received.

In turn, TCP is slower because for each SYN (send request) to connect and then TCP will wait for an ACK (acknowledgement) before data is sent.

### Check A Website is Up

#### Type in Command Line

`ping twitter.com`

#### My Ping Response

```
Pinging twitter.chrobinson.com [23.217.138.110] with 32 bytes of data:
Reply from 23.217.138.110: bytes=32 time=30ms TTL=55
Reply from 23.217.138.110: bytes=32 time=30ms TTL=55
Reply from 23.217.138.110: bytes=32 time=32ms TTL=55
Reply from 23.217.138.110: bytes=32 time=30ms TTL=55

Ping statistics for 23.217.138.110:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 30ms, Maximum = 32ms, Average = 30ms
```

### Ping Response Explained

The ping response is sending a packet out and asking if some-website is up and running (available).

## DNS

Stands for Domain Name System and it is run by ICANN.

ICANN stands for Internet Corporation for Assigned Names and Numbers.

DNS can be considered a large phone book for the internet and it maps domain names to IP addresses.

We need DNS because otherwise, the internet would not be as accessible for as many people if everyone had to remember IP addresses.

### TLD vs Domain vs Subdomain

TLD stands for top level domain and is it the (dot something) .com, .net, .org, etc. part of the website.

The domain is the twitter.com, frontendmasters.com, daphnelink.com, yourwebsite.com, etc. part.

A subdomain is something.maindomain.com. So, an example would be help.twitter.com.

The subdomain is affiliated with the main site, but from a user perspective, it looks like it can be a different website.

### Nameservers

Domains map to IP addresses, so we can easily type in twitter.com instead of the IP address that is mapped to twiter.com.

The mapping process is figured out by what is called DNS Resolvers.

The DNS Resolvers figure out the IP mapping by looking up the mapping information from Nameservers.

So, if you visit twitter.com in a browser, what happens behind the scenes is the DNS Resolvers will make a request to the Nameservers.

The Nameservers will say "Oh, I have seen this twitter.com before, let me find the IP address that matches". The Nameservers will find the IP address that maps to twitter.com and then the servers that are storing the Twitter website, data, users, etc. will be retrieved from the servers they are stored on and it will respond back to the browser with all the files/data for twitter.com.

## Traceroute

Instead of ping, which checks to see if a domain or IP is alive, traceroute gives you a map of every single server on the path to a given domain or IP.

On Windows, type command:

`tracert google.com`

On Linux, type command:

`traceroute google.com`

```
Tracing route to google.com [142.251.40.46]
over a maximum of 30 hops:

  1     4 ms     3 ms     4 ms  ATLANTALT33.chrobinson.com [192.168.1.254]
  2    21 ms    24 ms    20 ms  76-219-220-1.lightspeed.irvnca.sbcglobal.net [76.219.220.1]
  3    22 ms    21 ms    21 ms  70.232.228.89
  4    24 ms    20 ms    53 ms  12.242.115.21
  5    22 ms    22 ms    23 ms  12.255.10.174
  6    22 ms    24 ms    26 ms  216.239.57.67
  7    21 ms    24 ms    20 ms  142.251.233.235
  8    20 ms    55 ms    32 ms  lax17s55-in-f14.1e100.net [142.251.40.46]
```

Traceroute is very useful if your own website is down and are trying to determine what is wrong with your website.

If the hops die out closer to the given domain/IP, this could be an indicator a load balancer is failed or the given domain/IP is out.

If the hops die out closer to the beginning of the traceroute, like on the ISP, this might indicate the ISP is not resolving.

### ICMP (Internet Control Message Protocol)

Both ping and traceroute run ICMP requests, which are both types of healthchecks.

A server can be configured to not allow requests. A server can also be configured to not respond aka ignore requests.

For instance, if you try to run a traceroute on frontendmasters.com, you might see something similar to the below:

```
Tracing route to frontendmasters.com [54.213.95.63]
over a maximum of 30 hops:

  1     8 ms     5 ms     3 ms  ATLANTALT33.chrobinson.com [192.168.1.254]
  2    21 ms    20 ms    21 ms  76-219-220-1.lightspeed.irvnca.sbcglobal.net [76.219.220.1]
  3    21 ms    20 ms    21 ms  70.232.228.89
  4    71 ms    21 ms    41 ms  12.242.115.22
  5    27 ms    21 ms    23 ms  12.119.254.78
  6     *        *        *     Request timed out.
  7     *        *        *     Request timed out.
  8     *        *        *     Request timed out.
  9     *        *        *     Request timed out.
 10     *        *        *     Request timed out.
 11     *        *        *     Request timed out.
 12     *        *        *     Request timed out.
 13     *        *        *     Request timed out.
 14     *        *        *     Request timed out.
 15     *        *        *     Request timed out.
 16     *        *        *     Request timed out.
 17     *        *        *     Request timed out.
 18     *        *        *     Request timed out.
 19     *        *        *     Request timed out.
 20     *        *        *     Request timed out.
 21     *        *        *     Request timed out.
 22     *        *        *     Request timed out.
 23     *        *        *     Request timed out.
 24     *        *        *     Request timed out.
 25     *        *        *     Request timed out.
 26     *        *        *     Request timed out.
 27     *        *        *     Request timed out.
 28     *        *        *     Request timed out.
 29     *        *        *     Request timed out.
 30     *        *        *     Request timed out.

Trace complete.
```

If a website is ignoring ICMP requests, this is known as blackholing.

This means the server / website ICMP request have been set to 0.

So, in the instance of frontendmasters.com, it is ignoring ICMP requests, so we know the ICMP requests have been set to 0.

## Packets

A packet is information or more specifically metadata being transferred.

A good analogy for what a packet is, is mailing something in an envelope.

A standard envelope contains an address to and from somewhere and inside the envelope there is a letter. The letter would be the metadata in a packet.

## Net Neutrality

Net Neutrality is a trust system that says this data will send and receive from one location to another and trust it will get where it is going.

So, in regards to how the internet works, the internet runs over TCP/IP, which is the protocol everyone agrees on.

On the protocol are packets and packets are information everyone knows how to communicate with.

There are different types of packets, such as ICPM, which are essentially healthchecks like ping and traceroute.

All of these things rely on net neutrality. So, if I type in google.com into the browser, I trust packets will continously handed off to the next packet until the server resolves through DNS.

### Net Neutrality Debate

The great net netruality debate is whether or not the trust system should continue to be this free system of transmitting data, or should ISPs be allowed to charge based on where something is going.

## Servers

### VIM

VIM aka Vi Improved is a text editor.

VIM has 3 modes:

| Mode           | Mode Description               |
| -------------- | ------------------------------ |
| insert mode    | Text editing                   |
| command mode   | Primary mode to enter commands |
| last line mode | Searching, saving, exiting     |
