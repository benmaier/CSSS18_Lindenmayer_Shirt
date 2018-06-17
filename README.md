# Using Lindenmayer Systems to Generate a Fractal Logo

This repository takes a base png and generates a fractal structure using a Lindenmayer system.

The system is as follows

```
axiom = A
rules = { A -> [AraA][l+bB],
          B -> [BraA]
        }
```

 * `[` pushes a copy of the current coordinate system to a stack
 * `r` moves the coordinate system to vector _r_
 * `a` scales the coordinate system with ratio _a_
 * `]` removes the current coordinate system from the stack such that the following coordinate system is the one that had this one as an offspring.
 * `l` moves the coordinate system by vector _l_
 * `+` rotates the coordinate system by angle _alpha_
 * `b` scales the coordinate system with ratio _b_
 * `A` draws a copy of the image. 
 * `B` draws a copy of the image. 

For, e.g. `n = 3` iterations, the self-similar result is

```
[[[AraA][l+bB]ra[AraA][l+bB]][l+b[BraA]]ra[[AraA][l+bB]ra[AraA][l+bB]][l+b[BraA]]][l+b[[BraA]ra[AraA][l+bB]]]
```

## To play around with this

```
git clone https://github.com/benmaier/CSSS18_Lindenmayer_Shirt
cd CSSS18_Lindenmayer_Shirt
python3 -m "http.server" 1313
```

In your browser, open `localhost:1313`.

