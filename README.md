#intaments

> Instaments?

Instant Instruments, duh!

## Prefabricated Axoloti Instruments

In this repository you will find `/controllers` and `/instruments`

### Controllers
Controllers are Axoloti subpatches for your favorite controller. They include outlets that are mapped to the most common
configuration of the controller, making them instantly usable without messing with mappings.

### Instruments
Instruments are Axoloti subpatches with enough inlets to let you get started right away. The rule of thumb is, just
enough to be useful, not so much as to be overwhelming. 

For example, a drum machine, with enough drums to compose a drum track, and enough parameters to make it fit my music,
like the layout of a 909.

The point is, too much flexibility leaves people fiddling, versus creating. The idea of Instaments is to get users
creating tracks as quickly as possible. If they want to push things further, the Axoloti patcher awaits.

### Bringing it together
Now an instament isn't exactly 'instant', we still need to bring controller and intrument together. So that users can
audition instaments, there should always be a generic midi version, that does just enough that almost any controller
can use the instrament. These are the `/instaments`

## WHY

The [Axoloti](http://www.axoloti.com/) is the coolest thing in the world of DIY instruments. That's my opinion anyway.

On the surface, the Axoliti is:
  
  * Affordable
  * A versitile host for VA and Digital synthesis and effects
  * A versitile MIDI swiss army knife
  * Exandable through GPIO and Digital Busses.
  * Supported by the original author and a community of enthusiasts
  * Backed by thousands of great objects and subpatches to get you started.
  * Reusable! 

And yet I feel it could be more. Here's my thinking:

  1. I want a drum machine
  2. I have a spare (actually many) Axoloti
  3. Where's a good 909-like drum patch so I can add drums to my track
  4. Hmm nothing in the community forums matches my needs
  5. But there are lots of great drum objects
  6. Ok so I'll put those objects together
  7. And I'll create a patch that maps my controller (Beat Step Pro) to these drums
  8. And I'll pick useful parameters in the drums and map those too.
  9. ... Wait, what was I doing?

So as much as I love noodling with patches, my need was much more immediate, and I think there are artists out there
who would buy an Axoloti (or 5) if they also had immediate patches for different kinds of instruments. They might
not be the focus user for the Axoloti, but more sales might mean more money for Johannes Taelman to keep the platform going.
It also means wider adoption.

So I came up with a plan to make prefabricated Axoloti instuments.
