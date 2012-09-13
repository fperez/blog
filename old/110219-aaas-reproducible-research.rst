==================================================================
 Reproducible Research at the AAAS 2011 meeting in Washington, DC
==================================================================

**Update:** added links to other related posts, significantly expanded the
section on Git and Github for scientific work.

At this year's AAAS meeting, currently taking place in DC (in unseasonably warm
and sunny weather), `Victoria Stodden`_ from the statistics department at
Columbia, organized a symposium_ titled *The Digitization of Science:
Reproducibility and Interdisciplinary Knowledge Transfer* that was very well
attended.  She has put together a page_ with the full abstracts as well as
links to the individual slides.  On this site, I've posted the slides_ for my
talk, as well as an `extended abstract`_.

Lessons from the Open Source software world
===========================================

I have tagged this post with "Python" because my take on the matter was to
contrast the world of classic research/academic publishing with the practices
of open source software development, and what little I know about that (as well
as some specific tools I mentioned, like Sphinx_), I picked up from the world
of open source scientific Python projects I'm involved with, from IPython_
onwards.  My argument is that the tools and practices from the open source
community in fact come much closer to the scientific ideals of reproducibility
than much of what is published in scientific journals today.

.. _victoria stodden: http://www.stanford.edu/~vcs
.. _symposium: http://aaas.confex.com/aaas/2011/webprogram/Session3166.html
.. _page: http://stanford.edu/~vcs/AAAS2011
.. _sphinx: http://sphinx.pocoo.org
.. _ipython: http://ipython.scipy.org

The OSS world is basically forced to do this, because people across the world
are collaborating on developing a project from different computing
environments, operating systems, library versions, compilers, etc.  Without
very strong systems for provenance tracking (aka version control), automatic
testing and good quality documentation, this task would be simply impossible.
But many of these tools can be adapted for use in everyday scientific work; for
some use cases they work extremely well, for others there's still room for
improvement, but overall we can and should take these lessons into everyday
scientific practice.

In my talk, I spent a fair amount of time discussing the Git version control
system, not in terms of its technical details, but rather trying to point out
how it should not be viewed just as a tool for software development, but
instead as something that can be an integral part of all aspects of the
research process.  Git is a powerful and sophisticated system for provenance
tracking that automatically validates data integrity by design: Linus Torvalds
wanted to ensure that every commit operation is signed with a hash of its
contents *plus* the hash of its dependencies (for details on this, his
sometimes abrasive `Google Tech Talk about Git`_ is an excellent reference).
This simple idea ensures that a single byte change *anywhere* in the entire
repository can be detected autommatically.

I use Git for just about all my activities at the computer that require
manually creating content, with repositories not only for research projects
that involve writing standalone libraries, but also for papers, grant
proposals, data analysis research, and even teaching.  Its distributed nature
(every copy of the repository has all the project's history) makes it
automatically much more resilient to failures than a more limited legacy tool
like Subversion and its strong branching and merging capabilities make it great
for exploratory work (somehting that is painful to achieve with SVN).  Git is
also the perfect way to collaborate on projects: all members have full
versioning control, can commit work as they need it, and can make visible to
collaborators only what they deem ready for sharing (this is impossible to do
with SVN).  Writing a multiauthor paper or grant proposal with Git is a far
saner, more efficient and less error prone process than the common madness of
emailing dozens or hundreds of attachments every which way between multiple
people (for those who think Dropbox suffices for collaborative writing\: it's
like using a wood saw for brain surgery; Dropbox is great for many things and I
love it, but it's not the tool for this problem).  I have also used Git for
teaching, by creating a public repository for all course content and individual
repositories for each student that only the student, the teaching assistants
and myself can access.  This enables students to fetch all new class content
with a simple::

  git pull

instead of clicking on tens of files in some web-based interface (the typical
system used by many universities).  A single clone operation can reconstruct
the entire class repository on another computer if they need to use it in more
than one place or lose their old copy.  And when it's time to submitting
homework, instead of emailing or uploading anything, all they need to do is::

  git push

and the TAs have immediate access to all their work, including its development
history.  In this manner, not only is the process vastly smoother and simpler
for all involved, but the students learn to use version control as a natural
tool that is simply part of their daily workflow.

.. _google tech talk about git: http://www.youtube.com/watch?v=4XpnKHJAok8

I also tried to highlight the role played by the GitHub_ service as an enabler
of collaboration.  While Git can be used (and it is extremely useful in this
mode) on a single computer without any server support, the moment several
people want to share their repositories for collaborative work, some kind of
persistent server is the best solution.  GitHub, a service that is free for
Open Source projects and that offers paid plans for non-public work, has a
number of brilliant features that make the collaboration process amazingly
useful.  Github makes it trivial for new contributors to begin participating in
a project by *forking* it (i.e. getting their personal copy to work on), and if
they want their work to be incorporated into the project, they can make a *pull
request*.  The original authors then review the proposed changes, comment on
them (including making line-specific comments with a single click), and once
all are satisfied with the outcome, integrate them.  This is effectively a
public peer review system that, while created for software development, can be
equally useful for collaborative authorship of a research project.

.. _github: http://github.com

I should add, however, that I think there's still room for improvement
regarding Git as a tool for pervasive use in the scientific workflow. As much
as I absolutely love Git, it's a tool tailored for *source code* tracking and
its atomic unit of change is the line of code.  As such, it doesn't work as
conveniently when tracking for example changes in a paper (even if written in
TeX), where a small change can reflow a whole paragraph, showing a diff that is
much larger than the real change.  In this case, the "track changes" features
of word processors actually work better at showing the specific changes made
(despite the fact that I think they make for a horrible interface for the
overall workflow) [*Note*: in the comments below, a reader indicates that the
``--word-diff`` option solves this problem, though I think it requires a very
new version of Git, 1.7.2 at least.  But it's fantastic to see this kind of
improvement being already available].  And for tracking changes to binary
files, there's simply no meaningful diff available.  It would be interesting to
see new ideas for improving something like git for these kinds of use cases.

I wrapped things up with a short mention of the new `Open Research
Computation`_ journal, where Victoria and I are members of the editorial board,
as well as several well-known contributors to the scientific Python ecosystem,
including Titus Brown, Hans-Petter Langtangen, Jarrod Millman, Prabhu
Ramachandran and Gaël Varoquaux.

.. _open research computation: http://www.openresearchcomputation.com
.. _slides: http://fperez.org/talks/1102_aaas_reproducibility_fperez_slides.pdf
.. _extended abstract:
.. http://fperez.org/talks/1102_aaas_reproducibility_fperez_extabs.pdf


Other presentations
===================

I spoke after `Keith Baggerly`_ and Victoria.  Keith presented an amazing
dissection of the (ongoing) scandal with the Duke University `cancer clinical
trials`_ that has seen extensive media coverage.  This case is a bone-chilling
example of the worst that can happen when unreproducible research is used as
the base for decisions that impact the health and lives of human beings.  Yet,
despite the rather dark subject, Keith's talk was one of the most lively and
entertaining presentations I've seen at a conference in a long time.  Victoria
discussed the legal framework in which we can begin considering the problem of
reproducible computational research; she was instrumental in the NSF's new
grant guidelines now having a mandatory data management plan section.  She has
the unique combination of both a computational and a legal background, which is
very necessary to tackle this problem in a meaningful way (since licensing,
copyright and other legal issues are central to the discussion).

Afterwards, Michael Reich from the Broad Institute presented the GenePattern_
project, an impressive genomic analysis platform that includes provenance
tracking and workflow execution, as well as a plug-in for Microsoft Word to
connect documents with the execution engine.  While the Word graphical user
interface would likely not be my environment of use, the GenePattern system
seems to be very well thought out and useful.  The last three talks were by
Robert Gentleman of BioConductor_ fame, David Donoho --Victoria's PhD advisor
and a pioneer in posing the problem of reproducibility in computational work
together with Jon Claerbout, and finally Mark Liberman of U. Penn (see `Mark's
blog`_ for his take on the symposium).

.. _keith baggerly: http://odin.mdacc.tmc.edu/~kabaggerly
.. _cancer clinical trials:  http://bioinformatics.mdanderson.org/Supplements/ReproRsch-All
.. _genepattern: http://genepattern.org
.. _bioconductor: http://www.bioconductor.org
.. _mark's blog: http://languagelog.ldc.upenn.edu/nll/?p=2976

I think the symposium went very well; there was lively discussion with the
audience and good attendance.  A journalist made a good point on how
improvements on the reproducibility front are important for them, when they are
trying to do their job of reporting to a sometimes skeptical public the results
of scientific work.  If our work is made available with strong, credible
guarantees of reproducibility, it will be that much more easily presented to a
society which ultimately decides whether to support the scientific endeavor (or
not).

There is a lot of room for improvement, as Keith Baggerly's talk painfully
reminded us.  But I think that finally the climate is changing, and in this
case in the right direction: the tools are improving, people are interested,
funding agencies are modifying their policies and so are journals.
