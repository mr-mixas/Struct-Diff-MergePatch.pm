# NAME

Struct::Diff::MergePatch - JSON Merge Patch
([rfc7396](https://tools.ietf.org/html/rfc7396)) for perl structures

<a href="https://travis-ci.org/mr-mixas/Struct-Diff-MergePatch.pm"><img src="https://travis-ci.org/mr-mixas/Struct-Diff-MergePatch.pm.svg?branch=master" alt="Travis CI"></a>
<a href='https://coveralls.io/github/mr-mixas/Struct-Diff-MergePatch.pm?branch=master'><img src='https://coveralls.io/repos/github/mr-mixas/Struct-Diff-MergePatch.pm/badge.svg?branch=master' alt='Coverage Status'/></a>
<a href="https://badge.fury.io/pl/Struct-Diff-MergePatch"><img src="https://badge.fury.io/pl/Struct-Diff-MergePatch.svg" alt="CPAN version"></a>

# VERSION

Version 0.01

# SYNOPSIS

    use Struct::Diff::MergePatch qw(diff patch);

    $old = {a => {b => 1,c => [0],  d => 5},f => 2};
    $new = {a => {b => 1,c => [0,1],e => 6},f => 2};

    $diff = diff($old, $new);
    # {a => {c => [0,1],d => undef,e => 6}}

    patch($old, $diff);
    # $old now equal to $new

# EXPORT

Nothing is exported by default.

# SUBROUTINES

## diff

Calculate patch for two arguments:

    $patch = diff($old, $new);

Convert [Struct::Diff](https://metacpan.org/pod/Struct::Diff) diff to merge patch when single arg passed:

    $patch = diff(Struct::Diff::diff($old, $new));

## patch

Apply patch.

    patch($target, $patch);

# AUTHOR

Michael Samoglyadov, `<mixas at cpan.org>`

# BUGS

Please report any bugs or feature requests to
`bug-struct-diff-mergepatch at rt.cpan.org`, or through the web interface at
[http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Struct-Diff-MergePatch](http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Struct-Diff-MergePatch). I
will be notified, and then you'll automatically be notified of progress on
your bug as I make changes.

# SUPPORT

You can find documentation for this module with the perldoc command.

    perldoc Struct::Diff::MergePatch

You can also look for information at:

- RT: CPAN's request tracker (report bugs here)

    [http://rt.cpan.org/NoAuth/Bugs.html?Dist=Struct-Diff-MergePatch](http://rt.cpan.org/NoAuth/Bugs.html?Dist=Struct-Diff-MergePatch)

- AnnoCPAN: Annotated CPAN documentation

    [http://annocpan.org/dist/Struct-Diff-MergePatch](http://annocpan.org/dist/Struct-Diff-MergePatch)

- CPAN Ratings

    [http://cpanratings.perl.org/d/Struct-Diff-MergePatch](http://cpanratings.perl.org/d/Struct-Diff-MergePatch)

- Search CPAN

    [http://search.cpan.org/dist/Struct-Diff-MergePatch/](http://search.cpan.org/dist/Struct-Diff-MergePatch/)

# SEE ALSO

[Struct::Diff](https://metacpan.org/pod/Struct::Diff), [JSON::MergePatch](https://metacpan.org/pod/JSON::MergePatch),
[rfc7396](https://tools.ietf.org/html/rfc7396)

# LICENSE AND COPYRIGHT

Copyright 2017 Michael Samoglyadov.

This program is free software; you can redistribute it and/or modify it under
the terms of either: the GNU General Public License as published by the Free
Software Foundation; or the Artistic License.

See [http://dev.perl.org/licenses/](http://dev.perl.org/licenses/) for more information.
