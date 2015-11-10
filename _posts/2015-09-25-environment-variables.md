---
layout: post
title: Putting secrets in environment variables is stupid.
subtitle:
---

There seems to be this infatuation, especially in the Rails community, with
putting secret information inside environment variables. Now, even if I take
off my old crufty Solaris hat and ignore what the '-e' flag of ps means on
that platform: this is a stupid, pointless idea. The process environment is
not a secret.

The ostensible idea behind this is that if you pass in things in the
environment, you're protected from a scenario where someone breaks into your
machine and reads your presumably non-world-readable file containing your keys
or passwords. This is laughable for several reasons:

    * Files were designed to be secured with permissions. The environment, on
      the other hand, was never designed or intended to store secret
      information.

    * Unless you're passing shit into a Docker container, the environment
      variables are *already stored in a flat file* on the host.

    * If you passed your secrets in as an environment variable, and you use
      Linux, your secrets ARE ALREADY IN A FILE in /proc.

    * If someone pops a shell within your process, they can just run "env"
      anyway.

So just put your secrets in a file like a normal person. If you want to be
fancy, pass them to the process over a pipe from a higher privileged process,
but don't pretend that environment variables make things magically ephemeral.
