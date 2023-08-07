+++
title = "Week1.2 What I need to do to set up my machine?"
date = 2023-08-03
+++

 ordered a MacBook, but it wasn't ready for me yet.
Instead, I got this big, clunky Windows laptop.
It was heavy, you could easily kill someone or yourself just by carrying it.
I booted it up, and the first thing it did was to update Windows.
In the meantime, my manager gave me my AD login and told me to request admin rights.
After 30 minutes of Windows update and restarts, I finally saw the login screen.

I was able to log in, and it started updating Windows again. More waiting.
After 20 minutes, I was finally able to start setting up my machine.

Node was the first thing I wanted to install. "Oh wait, I can't," I then remembered.
I didn't have the permissions for that.
More waiting for IT support to set up my second AD account with admin rights.

After lunch, I finally got the admin account and was able to install Node and Git.
John then invited me to all the repos and groups in GitLab.
I was quite happy that we were using GitLab as CI/CD. At least, that's what I thought we were doing.

Now it was time for me to check out the code from GitLab. So I did the usual: created an SSH key and added it to GitLab.
I cloned the repo and wanted to install the npm packages. Jax said, "No, you can't just install with npm i."
He then explained to me that they have a monorepo, and I needed to use npm run full-install. He had written a script to
install all the needed dependencies. I ran the command, and I got an error. Something about certificates.
Jax then said, "Ah, yes, we have self-signed certificates. I'll email you the needed file, and you need to add it so that npm can use it."
He sent me the file via email, and I needed to add this to my environment: `export NODE_EXTRA_CA_CERTS=<PATH TO FILE>`, and
my .npmrc needed `strict-ssl=false`. After that, he said we have our own npm repo. It's some old, outdated JFrog server.

After all of this, I was finally able to run npm run full-install. It only took 22 minutes to finish.
This was the longest npm install I've ever seen. While it was installing, I asked Jax:
"Why do we need 32GB, and a desktop CPU to run our frontend?" We don't run the backend on our machine; we're connecting to one environment.
Jax answered, "Because we have a monorepo and a complicated setup, and Webpack needs a lot of RAM. Also, you can't run all the frontend processes at the same time."
I asked him, "What do you mean by 'all the frontends'?" Jax replied, "Yes, see, we have a lot of apps, and they have a lot of features. I'll show you once you can run the app."

Then I started the frontends, and the fans of the clunky laptop started spinning right away and wouldn't stop until I stopped the process for serving our frontends.
Yes, I wasn't running all of them, only the ones I needed.

After a build/startup time of around 3 to 5 minutes, I could finally see the app running.
I entered `localhost:3000`, and I could see nothing, but an error message that said something about the JSON not being parsed.
John then said, "Oh, it looks like you have no access rights or role in the app."
I asked him how he knew that. He just said, "You just know after a while."

He then started the app on his laptop and added me to the one test environment that all the frontend devs are using.
Then he said, "If I forget to add you tomorrow, ping me please."
I looked confused at him. He continued, "Yeah, our test environment is synced every night.
Someone has to add you to the AD, and then our system needs to import your user. This can sometimes take 2 weeks."
I just said, "Okay." Since my brain now couldn't process what he just said.

Jax then said, "Okay, let's call it a day. It's time to go home. We have the system running. This was super fast. Only 2 days. Usually, this takes at least a week."

Again, my mind couldn't process what he just said. Two weeks to start a frontend?

I left the office again with mixed feelings. On the one hand, I was glad that I had finally gotten the system running. But, I was baffled by the amount of time and effort it had taken.
