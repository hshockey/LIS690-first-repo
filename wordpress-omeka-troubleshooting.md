# Wordpress and Omeka Troubleshooting

When I first did the wordpress and omeka installations, everything worked fine and the
links and I was able to connect Omeka to Wordpress. In Teams, I linked my wordpress and
other students responded that it was laid out nicely. 

However, once I was done with the Omeka install, linked it to Wordpress, and submitted the
assignment, for some reason the server wouldn't connect anymore. This was right after my
"trial" period ended on Google Cloud and I officially began the regular account. When this
happened, my VM stopped and when I restarted it, there was a new IP address associated with
the account. This is where everything started to go wrong. The server for my wordpress and
omeka existed, but it didn't connect through the URL. While the link from wordpress to
omeka didn't work, the direct link to omeka did. The following is my URL for wordpress
that still will not work even with the new IP address

`http://34.30.41.150/wordpress`

And the direct link to Omeka, which **is** working

`http://34.30.41.150/omeka-3.1.2`

## Troubleshooting process

1. At first, I checked my logs on Google Cloud to make sure there weren't any expections
that might be causing this issue. Nothing came up beyond the typical pings for starting
the VMs and connecting to the sites. 

2. Then, I thought maybe since the IP address changed, I would have to change that in the
installation of wordpress on my VM. However, as I went through all the notes for class,
there was nowhere that discussed a moment where we added our own IP address aside from in
the browser. Additionally, the IP address, when used by itself and not linked to wordpress,
still sent me to a working server. 

3. I googled troubleshooting suggestions from others who might've had the same issue, but
not surprisingly, everyone's examples were different and since I didn't want to mess up
what I already had any further, I didn't try to change the code that was already included.

4. I then tried to stop and restart my VM again, to make sure it wasn't some weird glitch. 
This did nothing, even when I included the newest IP address in the system. When I enter
the URL for wordpress, it technically acts like it wants to connect but won't.

5. Finally, I cleared the cache on my browser, just in case. Still nothing. 

### Creating New VM

When nothing else worked, I decided I would create a whole new VM so I could at least
reinstall everything and start from scratch. 

This process went fine. I was able to add the LAMP stack and do the wordpress installation 
per the Professor's instructions. 

I was able to start editing my wordpress website in the browser like normal, but when I 
clicked away for a moment and tried to go back, it did the same thing the other server did.
It would no longer connect. This is where it seemed really weird, because I was in the
middle of customizing my wordpress and everything was fine. 

Ultimately, after this moment, I stopped working on any of it. Obviously either I was doing
something weird or maybe Google Cloud was experiencing a weird glitch. I have no idea, but 
nothing I did helped. 

#### Omeka

Omeka is up and running just fine on my original VM when it is linked directly, as stated
above, but since I cannot open wordpress, I'm not able to link it together. 

This has definitely been discouraging, especially since I was really excited I was able to 
successfully perform these assignments and get a result before things went wrong.
