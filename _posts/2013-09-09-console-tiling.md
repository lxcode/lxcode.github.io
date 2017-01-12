---
layout: post
title: dvtm + iTerm2
subtitle: A usable console tiling solution
---

Working so much with iOS, I've had to be primarily on a Mac for the last year.
I've been spending most of my time in X, as dwm + terminals has been my primary
working environment for years. However, having upgraded to a Retina Macbook, X
looks freaking horrible compared to all the other applications. As such, I've
tried a couple different solutions to replicate dwm+urxvt functionality within
iTerm2.

Native iTerm2 panes.
--------------------
<http://www.iterm2.com>

Using iTerm's builtin panes, you can do horizontal or vertical splits and
switch between them. I configured iTerm to use cmd-j and cmd-k to navigate
between them, and configured text dimming on inactive panes. All in all, this
is usable, but the real shortcoming is that it isn't really real tiling window
management. Splits all have to be manually configured, are a pain in the ass to
rearrange, and you can't temporarily full-screen a pane. Wasn't scratching my
dwm itch.

tmux.
-----
<http://tmux.sourceforge.net/>

I use tmux on my shell server, and I'm pretty used to it. However, the split
functionality has the same kind of shortcomings, where rearranging and resizing
is a pain, and you have to use an escape sequence before entering a command,
meaning 3 keypresses just to move to another pane. It has the advantage of
mixing windows and panes in a way that feels more natural to me than iTerm, but
otherwise, it's more of a multiplexer than a window manager. Also, I use tmux
on a remote host to attach to a long-running session, and nesting two tmux
instances is even more painful.

dvtm.
-----
<http://www.brain-dump.org/projects/dvtm/>

dvtm is essentially dwm for the terminal --- it does dynamic window management,
rearranging windows for you in a stack instead of you having to decide where to
split everything and rearrange manually. It still has the irritation of
requiring too many keystrokes for basic actions, though. It uses ctrl-g as its
escape sequence by default, which is annoying to use, but I can run tmux under
it and not have to double-escape commands (and yes, I realize I could have two
separate tmux configs, but I don't want to; I'm too used to ctrl-a when in
tmux, and would have to keep them both straight). So, it's *almost* great, but
a toss-up between this and using native panes when it comes to convenience.
Then, I discovered:

<http://tangledhelix.com/blog/2012/04/28/iterm2-keymaps-for-tmux/>

Ding! Brilliant. Now I can configure my keybindings in iTerm so that the keys I
use in dwm will perform the exact same actions in dvtm. I kept the stock escape
sequence of ctrl-g to avoid clobbering tmux commands, and configured iTerm to
send 0x07 0xwhatever for cmd-j/k/l/h/i/x/t/g/b/enter. Now I navigate simply and
quickly with the command key instead of two-step escaped commands, and can run
a remote tmux session with no problem --- I never have to hit ctrl-g at all.
And I get to look at pretty Retina fonts. Scrolling is pretty slow, and there
are some artifact issues, but I think it's worth it.

I've put my iTerm2 config here:

<https://github.com/lxcode/dotfiles/blob/master/com.googlecode.iterm2.plist>

Ideally, I'd like to see iTerm integrate dynamic tiling, but for the moment,
this is about as close as you can come.
