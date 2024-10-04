# SQL::Formatter ![static](https://github.com/uperl/SQL-Formatter/workflows/static/badge.svg) ![linux](https://github.com/uperl/SQL-Formatter/workflows/linux/badge.svg)

Format SQL using the rust sqlformat library

# SYNOPSIS

```perl
my $f = SQL::Formatter->new;
say $f->format('select foo.a, foo.b, bar.c from foo join bar on foo.a = bar.c where foo.b = 2');
```

prints:

```
SELECT
  foo.a,
  foo.b,
  bar.c
FROM
  foo
  JOIN bar ON foo.a = bar.c
WHERE
  foo.b = 2
```

# DESCRIPTION

Pretty print SQL using the rust crate `sqlformat`.

# ATTRIBUTES

The formatting options can be specified either when the object is constructed, or later using accessors.

```perl
my $f = SQL::Format->new( indent => 4 );
$f->indent(4);
```

- indent

    Controls the length of indentation to use.  The default is `2`.

- uppercase

    When set to true (the default), changes reserved keywords to ALL CAPS.

- lines\_between\_queries

    Controls the number of line breaks after a query.  The default is `1`.

# METHODS

## format

```perl
my $pretty_sql = $f->format($sql);
```

Formats whitespace in a SQL string to make it easier to read.

# AUTHOR

Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2024 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
