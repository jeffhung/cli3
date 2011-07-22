CLI3 - Command Line Interface 3
===============================

For a long time, I am looking for good and popular command line parser to
ease command line tool developments in Java.  However, none satisfies me.

Apache Commons CLI is simple, elegant, and popular. But it is too limited
that cannot support common design such as sub-command.  And its successor,
CLI2, is never finished or released according to its official site.  Since
I do not know any other good and popular implementation, I decide to make
my own one.

Ideas
-----

Here are some thoughts about how CLI3 should be designed:

* Should be able to integrate with Apache Commons Configuration or any
  other configuration framework.
  
  Since command line will change program behavior, it should be considered
  part of the configuration system, too.  For example, the Boost C++
  Program Options library demonstrates how the configuration system and
  command line processing could be integrated together well.
  
  However, I would like to narrow the scope first.  So, I am not planning
  to develop a huge framework that covers both configuration and command
  line processing.  Integrating with existing configuration framework
  become a good alternative approach.  After all, configuration is much
  complex than command line processing.

* Should promote good command line interface design.
  
  There could be many guidelines, and exceptions.  I will just list a few
  here and describe in detail in later section:

  - xargs(1) friendly
  - consistent positional argument order
  - support common pattens, such as sub-command
  - consistent behavior/direction between arguments and standard in/out.
  
  I believe there are many materials on Internet, too.  However, although
  I will search for these existing, popular, and recommended command line
  interface design patterns, I may not adopt everything.  Instead, I would
  like to verify these guidelines based on my preferences.  After all,
  this is my framework and I may use it in many places.
  
  How the Java framework be design to *promote* good design may be hard.
  That may become the major bottleneck of development of this framework.

* Prefer declarable over programmable.
  
  The specification of command line interface should be *declared* instead
  of *programmed*.  It would be good if the declarations in code look like
  common man page layout.  This is hard to design, too.  I know.

* Can automatically generate usage lines, help description, and man page
  synopsis and option lists.
  
  This may need to integrate with the configuration framework.  Since the
  command line options and arguments should share the same semantic and
  description with configuration framework.
  
  The command line interface may have to follow configuration framework.
  Because the behaviors that command line interface can control, is
  usually a sub set of full configurable option set.

* Is extensible by adaptive program components, to allow compositioin of
  features now and the future.

(TBD)



