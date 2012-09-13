==============================================
 Guido van Rossum at UC Berkeley's Py4Science
==============================================

**Update:** Quick links

   * Video_ of the entire session. The talks cover the first 50 minutes, and
     Guido's part starts at the 54 minute mark.
   * A `page with all the slides`_ on my site.
   * Guido also blogged_ his impressions.
   * Blog posts by `Jarrod Millman`_ and `Matthew Brett`_.

.. _page with all the slides: http://fperez.org/py4science/2009_guido_ucb
.. _blogged: http://neopythonic.blogspot.com/2009/11/python-in-scientific-world.html
.. _Jarrod Millman: http://jarrodmillman.blogspot.com/2009/11/visit-from-guido-van-rossum.html
.. _Matthew Brett: http://nipyworld.blogspot.com/2009/11/guido-van-rossum-talks-about-python-3.html

On November 4 2009, we had a special session of our informal Py4Science_
seminar where Guido van Rossum visited for an open discussion regarding the
uses of the Python language in scientific research. Guido had expressed his
interest in discussing the work that various scientists do with Python but
mentioned that instead of a formal talk, he would prefer a format that allowed
for more interaction with the audience.  We agreed that a good plan would be
for us to present a rapid-fire sequence of very short talks highlighting
multiple projects so that he could get a good "high altitude" view of the
scientific python landscape, leaving then ample time for discussions with the
audience.

.. _Py4Science: https://cirl.berkeley.edu/view/Py4Science

Guido has already posted `his impressions`_ of the visit, and so have my
colleagues `Jarrod Millman`_ and `Matthew Brett`_, so I'll try to provide a
complementary view here without too much repetition.

.. _his impressions: http://neopythonic.blogspot.com/2009/11/python-in-scientific-world.html
.. _Jarrod Millman: http://jarrodmillman.blogspot.com/2009/11/visit-from-guido-van-rossum.html
.. _Matthew Brett: http://nipyworld.blogspot.com/2009/11/guido-van-rossum-talks-about-python-3.html

We gathered for lunch first with a small group and had a very interesting
discussion on various topics; we had a chance to talk in some detail about the
transition to Python 3 for Numpy, something a number of people have started to
think about seriously.  Numpy is pretty much a 'root dependency' for so many
scientific projects, that until it makes the jump it will be very difficult for
anyone else in science to seriously consider Python 3.  Understandably, Guido
would like to see some movement from our community in this direction, and he
offered useful guidance.  In particular, he said that in the core Python-dev
team there might be enough interest that if we ask for help there, we might
find developers willing to pitch in and provide some assistance.  He also
expressed some disappointment that `PEP 3118`_, which was accepted with our
interests in mind, still hadn't been fully implemented.  Limited manpower is
the simple reason for this situation, but fortunately Jarrod mentioned that
there's a good plan to address this in the near future.

I had a chance to quiz Guido about something I've wondered for a while: Python
has unusually good number types in its core (arbitrary length integers,
extended precision decimals and complex numbers), but the integers divide
either into the integers (the truncating behavior of Python 2.x) or into the
floats (in 3.x).  While the 3.x division is an improvement, I would have really
liked to see Python go to native rationals; for one thing, this would make the
Sage 'language' (by which I mean the extensions Sage makes to pure Python)
behave like Python in algorithms involving integers, eliminating a recurring
source of confusion between the two.  I also happen to think it would be a
'better' behavior, though there are valid reasons also for someone to expect a
more 'calculator-like' answer to divisions like 1/2, who might be annoyed if
they get 1/2 back instead of 0.5.  While obviously such changes will not be on
the table for a long while (and I should say here that I am very happy with the
planned moratorium to core language changes, as I hope that will allow a more
focused effort on the needs of the standard library), it was interesting to
hear Guido's approach to this question as one that could be handled via
overloadable literals rather than a change of integer semantics.  I'd never
thought of that, but it's an intriguing idea... Something to think about for
when we start looking at Python 4000 :)

.. _PEP 3118: http://www.python.org/dev/peps/pep-3118

We then headed over to the official presentation, where we managed to cram 14
talks in 50 minutes and then had a full hour of open conversation with Guido,
where the audience asked him questions on a number of topics.  You can see a
complete video_ of the entire session: after 50 minutes of talks we have a
transition, and Guido's section starta at the 54 minute mark. On my website I
have posted_ a page with all the slides for these mini-talks.

I presented an overview_ introduction and material on behalf of 4 others who
were not present locally, but coincidentally, `William Stein`_ of Sage_ fame
was on campus to give a talk in the same building almost at the same time, and
he could present the Sage slides directly. `Ondrej Certik`_ from SymPy_ was
able to make the trip from Reno, completing our out-of-town speakers.  The
other 7 presentations were from a number of local speakers (from various
departments at UC Berkeley and Lawrence Berkeley National Laboratory, just up
the hill from us).

.. _overview: http://fperez.org/py4science/2009_guido_ucb/fperez_py4science_overview.pdf
.. _video: http://www.archive.org/details/ucb_py4science_2009_11_04_Guido_van_Rossum
.. _posted: http://fperez.org/py4science/2009_guido_ucb/index.html

.. _William Stein: http://wstein.org
.. _sage: http://sagemath.org
.. _Ondrej Certik: http://ondrejcertik.blogspot.com/
.. _sympy: http://code.google.com/p/sympy

I have received very good feedback from several people, and I am really
thankful to all the speakers for being so attentive to the time constraints,
which let us pack a lot of material while leaving ample time for the discussion
with Guido.  My intention with this was to really provide Guido with a broad
understanding of how significant Python's penetration has been in scientific
computing, where many different projects from disciplines ranging from computer
science to astronomy are relying heavily on his creation.  I wanted both to
thank him for creating and shepherding such a high-quality language for us
scientists, and to establish a good line of communication with him (and
indirectly the core python development group) so that he can understand better
what are some of the use patterns, concerns and questions we may have regarding
the language.

I have the impression that in this we were successful, especially as we had
time after the open presentations for a more detailed discussion of how we use
and develop our tools.  Most of us in scientific computing end up spending an
enormous amount of time with open interpreter sessions, typically IPython_ ones
(I started the project in the first place because I wanted a *very good*
interactive environment, beyond Python's default one), and in this work mode
the key source of understanding for code are good docstrings.  This is an area
where I've always been unhappy about the standard library, whose docstrings are
typically not very good (and often they are non-existent).  We showed Guido the
fabulous Numpy/Scipy `docstring editor`_ by Pauli Virtanen and Emmanuelle
Gouillart, as well as the fact that Numpy has an actual `docstring standard`_
that is easy to read yet fairly complete.  I hope that this may lead in the
future to an increase in the quality of the Python docstrings, and perhaps even
to the adoption of a more detailed docstring standard as part of `PEP 8`_,
which I think would be very beneficial to the community at large.

In the end, putting all this together took me a lot more time than I'd
originally planned (I think I've had this same problem before...), but I am
very pleased with the results.  Python has become a central tool for the work
many of us do, and I am really happy to establish a good dialogue with Guido
(and hopefully other core developers), which I'm sure will have benefits in
both directions.

.. _IPython: http://ipython.scipy.org
.. _docstring editor: http://docs.scipy.org/numpy/Front%20Page/
.. _docstring standard: http://projects.scipy.org/numpy/wiki/CodingStyleGuidelines#docstring-standard
.. _pep 8: http://www.python.org/dev/peps/pep-0008

