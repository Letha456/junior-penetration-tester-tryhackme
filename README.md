# Infrastructure Pen Test
## Name: Sipho Sehlapelo
The first thing I was taught was that I should not think of pen testing as a skill, rather as a way of thinking, and I might need to be flexible with my thinking or the way I approach things. For example, today I might think like a programmer, tomorrow a SOC, based on the conditions or my intentions.

Let's get into the lesson. Infrastructure penetration tests, also known as infra pentests, is where you make security assessments or pentests on devices on a network such as firewalls, servers, etc.

## 1. Enumeration

This is the first step every pen tester takes before going deep into it. To enumerate basically means that you are gathering as much information about whatever you are trying to pen test. This could be the type of services, ports, versions that are running on your network or server before making a decision. The point is that you should never make assumptions.

The tool I used for this was nmap.

So this is the command I used to enumerate:

```
nmap -sV -sC -oN scan.txt [machine IP address]
```

What this command is saying is that it basically scans the server for any open ports or services running on the server and extra details about authentication methods, and saves the output in a file called scan.txt.

<img width="1003" height="628" alt="Screenshot 2026-07-14 123950" src="https://github.com/user-attachments/assets/744930cb-eaa3-4680-91d7-ce62df265df5" />


From the results, I found 2 TCP ports open, 22 and 6667.

Now what I was taught is that I don't just look at the results line by line, I ask myself questions:

- Are there any services outdated?
- Is there any misconfigurations?

Then I go back to the results I found from nmap and use Google to search their versions and exploits, for example, OpenSSH 9.6p1 exploit.

And these are the results from google:
<img width="1042" height="710" alt="Screenshot 2026-07-14 124934" src="https://github.com/user-attachments/assets/85059586-86b9-48e2-a638-2d4532ec339b" />

Alternatively, I was also taught I can use Searchsploit, which is a CLI tool that lets you search Exploit-DB's offline database of public exploits.
