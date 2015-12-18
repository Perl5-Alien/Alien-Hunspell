# Alien::Hunspell

Install hunspell

# SYNOPSIS

Build.PL:

    use Alien::Hunspell;
    use Module::Build;
    
    Module::Build->new(
      ...
      extra_compiler_flags => Alien::Hunspell->cflags,
      extra_linker_flags   => Alien::HunSpell->libs,
      ...
    )->create_build_script;

Makefile.PL:

    use Alien:Hunspell;
    use ExtUtils::MakeMaker;
    
    WriteMakefile(
      ...
      CCFLAGS => $alien->cflags,
      LIBS    => $alien->libs,
      ...
    );

FFI::Platypus:

    use Alien::Hunspell;
    use FFI::Platypus;
    
    my $ffi = FFI::Platypus->new(
      lib => [Alien::Hunspell->new->dynamic_libs],
    );
    ...

# DESCRIPTION

This module provides the spelling library Hunspell.  It will either 
detect it as provided by the operating system, or download the source 
from the Internet and install it for you.  It uses [Alien::Base](https://metacpan.org/pod/Alien::Base).

# AUTHOR

Graham Ollis &lt;plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2015 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
