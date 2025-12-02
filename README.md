# Mini-Tenor Guitar

![3d image of the tenor guitar](tenor-top.jpg)

This is a mini-sized 4-string tenor guitar, intended to be strung using either nylon strings, or extra-light
gauge metal strings.

Everything is printed, _except_:

* a set of tuners with 10mm posts. (I use [these](https://www.amazon.com/gp/product/B0789YL6JF/ref=ppx_yo_dt_b_search_asin_image?ie=UTF8&psc=1).)
* A set of light or extra-light steel tenor banjo or tenor guitar strings. These should
  be strings intended for a CGDA tuning.
* A 12 1/4 inch truss rod (I used [this from StewMac](https://www.amazon.com/gp/product/B07HPBZ3NH/ref=ox_sc_act_title_1?smid=A1BA2XBPZFTT2S&psc=1)).
* 2 m4x60mm screws to attach the neck to the body.
* 2 m4 hex nuts.
* a 4x1mm carbon fiber rod, used to reinforce the body inside of the vertical brace.

Assembly should be pretty obvious.

I recommend printing this from PLA. In my experiments, PLA is by far the
best material that I've tried. PETG has too much flexibility, which seems
to absorb some of the resonant vibrations in the body; ABS adhesion issues
leave tiny micro-gaps in the body which completely ruin the tone.

## The Model

I started with a model written in standard OpenSCAD. That was a bit of a mess; I rewrote it partially using the BOSL libraries for OpenSCAD, which was a big improvement, but I was still struggling to make it come out the way I wanted, because honestly, OpenSCAD is a pretty terrible language.

So I wrote my own 3d modelling language.

The latest version is implemented in [Simplex](https://github.com/MarkChuCarroll/simplex), a 3d modelling
language that I built on top of the Manifest library. This
version of the model is contained in the file "mtenor.s3d".

The running the simplex model through the interpreter, you'll
get a collection of products:

* `mtenor-out-body-tail.stl`: the bottom-most section of the body.
* `mtenor-out-body-center.stl`:  the center section of the body.
* `mtenor-out-body-neck.stl`: The section of the body where the neck
  is attached.
* `mtenor-out-fretboard-full.stl`: a single-piece fretboard for large printers.
* `mtenor-out-fretboard-[ab].stl`: the fretboard split into two pieces for
   printing on normal-sized 3d printers. This includes guide-holes where
   you can insert 5mm pieces of filament as alignment guides, and cutouts
   for registration/alignment with the neck. The registration pegs are
   included in `mtenor-out-mist_bits.stl`.
* `mtenor-out-neck-[abc].stl`: the neck, divided into three printable pieces.
  Like the fretboard, this includes registration holes to use filament to
  align the sections for gluing.
* `mtenor-out-misc_bits.stl`: support plates, registration pegs, and fretboard
  inlays for assembly/glue-up.
* `mtenor-out-assembled.stl`: An image of the fully-assembled guitar, to show
  how the pieces should line up.
* `mtenor-out-bridge.stl`: a set of three different bridges; choose the one that
  gives you the most comfortable string-action.
* `mtenor-out-stand.stl`: a work-in-progress stand for supporting the guitar
  when you're not playing it.
