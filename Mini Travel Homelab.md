1. The Mini Travel Homelab

 What is it? This homelab is for people who are new to IT or have an interest in
homelab and don't want to spend an upfront cost but also do not want to setup a
fully racked server using an eBay bought R730 which consumes a lot of electricity
and can be loud. We will be using a raspberry pi instead of the rackserver and
raspberry pi can be versatile for other projects however if you want to have a
powerful homelab but compact and still portable you can get an intel NUC on eBay
or amazon. What motivated me to start this was homelab have been my favorite
although we have cloud and is easier to have your servers on there for safer backup
and natural disaster I hate paying per month to have my server on there but I also
like to know hands on the psychical aspect of it and getting to know more on LAN
network to connect a device to the WAN internet.

2. Goals & Requirements
Goals:

o Create an isolated lab network for testing.

o Have a portable setup for secure travel.

o Help newcomers into IT or into Homelab/Infrastructure

4. The Gear – Hardware Showcase
![2](https://github.com/user-attachments/assets/8d4db494-a21a-41fc-91bc-0f3eea2a41d7)

Router: GL.iNet GL-MT3000 (Beryl AX)
Server: Raspberry Pi 5 with Active Cooler
Storage: 256GB SD Card

If you buy on amazon, you can see the price history and Maby save cost if you time the right
price by using CamelCamelCamel.com, the raspberry pi 5 price was $90. I waited till it
dropped, then I bought it.
![3](https://github.com/user-attachments/assets/7db231ee-f11a-4c93-ab54-e657d4027370)

4. The Blueprint – Network Diagram & Configuration
![4](https://github.com/user-attachments/assets/e616c336-1d67-4192-9421-27a3e53a2bb4)

5. The Brains – Software & Services Stack & AI
• Stack:
o Operating System: Ubuntu Server
o Orchestration: Docker
o Services: None at the moment but will expand and add services in the
future.
• AI:
I used AI to help guide me in setting up ubuntu server on the raspberry pi 5 as this is
my first time in setting up a homelab on raspberry pi, previously I have setup on a
promox server and used AI to help me in setting up a VPN service but not without
trouble I was still able to accomplish the task at hand. It is recommended to tell the
AI what you want all upfront and strictly as the AI will take everything literally. You
can fine tune it later if you must end up troubleshooting later.
o ”How can I setup ubuntu server on raspberry pi 5 I have a 256GB SD card
I also have Gl.inet as a router that the raspberry pi 5 will connect to by
ethernet this is in case any complication happens as we want the
raspberry pi 5 to be able to have access to the internet.”
![5](https://github.com/user-attachments/assets/df577088-dad3-4479-8c80-2dd8f43b2702)

6. The Journey – Challenges & Solutions
• Originally I wanted to use an M.2 SSD that I use to use in a gaming computer that I
don't use anymore onto the raspberry pi 5 and after 5 hours of research I have found
out this SSD does not work on the raspberry pi 5 on a fourm post and it's probably
because the speed is to fast it's an M.2 Gen4 after all.
• So instead of using the M.2 SSD, I decided to use the 256GB SD card instead of the
M.2 SSD.

7. The Payoff – What It Does & Use Cases
• My daily use.
o Mess with docker
o Testing environment
o Used as a honeypot

8. Conclusion – Lessons Learned & Future Plans
• Summary: My favorite part from doing this is learning more on how to mess with
raspberry pi and learned to format the SD card and into booting up an ubuntu server
on the raspberry pi I also learned that M.2 SSD cards even Tho works on PC may not
work on every hardware (such as the raspberry pi). For now, I use the raspberry pi 5
to mess around with docker stuff as running virtual machines on it can be too heavy
or won't work.
• Future Ideas: Add a M.2 SSD on the raspberry pi 5, VPN, Honeypot and mess
around with a network virus in the future ( )
• Final Thought: I would recommend this setup to people starting in IT or who have
an interest in homelab or have a raspberry pi sitting in the closet collecting dust.
