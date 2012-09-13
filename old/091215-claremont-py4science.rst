=====================
 Py4science teaching
=====================

It's pretty clear to me that Python is rapidly growing in acceptance as a
computational platform at universities everywhere.  I recently heard from `Josh
Bloom`_ at UC Berkeley astronomy that his proposal for a short 'boot camp'
course at the beginning of the Fall semester was approved.  This is excellent
news, last year I taught `something similar`_ for neuroscience students and
postdocs, and I'm glad to see the campus adopting python further as a key
component of the computational training the science students receive.

.. _Josh Bloom: http://astro.berkeley.edu/~jbloom/
.. _something similar: http://fperez.org/py4science/workshop_berkeley_2008.html



John Hunter and I just completed a few days ago teaching another such workshop
at the Claremont Colleges, supported by an NSF grant that `John Milton`_,
(J. Hunter's PhD advisor) has for exposing undergraduates to a number of
research-related experiences.  This grant supports summer research internships
where two undergrads visit together a research lab elsewhere to work
independently on a project, which has already resulted in some really neat
projects, as well as our teaching of scientific python tools (we were also
there in 2008 and hopefully will continue next year).

.. _John Milton: http://faculty.jsd.claremont.edu/jmilton/

I have to say that I really enjoy teaching this type of workshop, especially
now that the core tools are fairly mature, installation isn't the problem it
used to be, and we have a chance of presenting interesting examples to the
students from the very beginning.  John Hunter is a phenomenal lecturer, with a
real knack for illustrating interesting concepts on the fly, in a very natural
manner that is honestly similar to how exploratory work is *actually* done in
real research, where you run a bit of code, plot some results, print a few
things, code some more, etc.  In the picture above, he was working through some
of the `matplotlib image tutorial
<http://matplotlib.sourceforge.net/users/image_tutorial.html>`_, which gave us
an opportunity to find and fix a small bug in how the luminance histogram was
being computed (the current form is correct).  Every one of these students
probably has a digital camera these days (if nothing else, in a cell phone), so
an example like this is a great way to connect something they are used to with
mathematical and programming concepts.


This one is from a great illustration of random numbers and simple statistics.
John built up interactively a simulation of random walks, working up from a
single (one-dimensional) walker to a group of them, comparing the simulation
results with the analytical predictions for various quantities (like mean and
variance), and also explaining to the students how these squiggly lines could
be considered a model of price fluctuations over time.  In this manner, he
connected the somewhat abstract statistical concepts to something the students
could relate to, namely the risk of an investment making a profit or a loss
after a certain period.

We also talked about FFTs, dynamical systems, error analysis, data formats, and
a few other things.  It was very encouraging to have most of the students
return on the second day, considering how this was a completely optional
activity for them, covering an entire weekend (with morning lectures both days)
right before they had to start diving into their finals.  But they were a smart
and enthusiastic bunch, and I hope that the workshop gave them some useful
starting points they can then develop on their own as they get involved in
research projects.

These are just two examples of how we are now seeing Python's acceptance in
university computing growing.  We have a lot of work still ahead of us, but
it's really encouraging to see how far we've come from the days when building
scipy was a black art, IPython was little more than a different prompt for the
python shell and matplotlib could only do basic line plots on top of libgd.  We
now have tools that provide a complete computational environment for teaching
and research, and things are only getting better...
