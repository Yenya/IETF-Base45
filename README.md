# NAME

QRCode::Base45 - Base45 encoding used in QR codes

# VERSION

Version 0.01

# SYNOPSIS

    use QRCode::Base45;

    my $text_for_qrcode = encode_base45($binary_or_utf8_data);
    my $binary_data = decode_base45($text_from_qrcode);

# DESCRIPTION

This module handles encoding/decoding of Base45 data,
as described in
[draft-faltstrom-base45-06](http://www.watersprings.org/pub/id/draft-faltstrom-base45-06.html).
Base45 is used especially in QR codes, for example in European vaccination
certificates.

## encode\_base45

Takes an arbitrary string as argument, and returns the Base45 representation
of it. Character strings (as opposed to byte strings) are encoded to bytes
as UTF-8.

For zero-length input strings (undef or '') an empty string ('') is returned.

## decode\_base45

Takes a textual Base45 representation of data, and tries to decode it.
Returned value is a byte string (as this function cannot possibly know
whether the content should be interpreted as bytes or UTF-8).
The caller has to decode the returned byte string to characters afterwards,
if needed.

For zero-length input strings (undef or '') an empty string ('') is returned.

For invalid inputs, such as strings of length 3n+1 or characters
outside of the Base45 alphabet, this function croak()s.

# AUTHOR

Jan "Yenya" Kasprzak, `<kas at yenya.net>`

# BUGS

Please report any bugs or feature requests to `bug-qrcode-base45 at rt.cpan.org`, or through
the web interface at [https://rt.cpan.org/NoAuth/ReportBug.html?Queue=QRCode-Base45](https://rt.cpan.org/NoAuth/ReportBug.html?Queue=QRCode-Base45).  I will be notified, and then you'll
automatically be notified of progress on your bug as I make changes.

The Base45 encoding is relatively new. After it is standardized
and maybe used elsewhere apart from QR codes,
this module should probably be moved to some other namespace,
such as IETF:: or RFCxyzq::.

# INSTALLATION

To install this module, run the following commands:

        perl Makefile.PL
        make
        make test
        make install

# SUPPORT

You can find documentation for this module with the perldoc command.

    perldoc QRCode::Base45

You can also look for information at:

- Github repository

    [https://github.com/Yenya/QRCode-Base45](https://github.com/Yenya/QRCode-Base45)

- RT: CPAN's request tracker (report bugs here)

    [https://rt.cpan.org/NoAuth/Bugs.html?Dist=QRCode-Base45](https://rt.cpan.org/NoAuth/Bugs.html?Dist=QRCode-Base45)

- CPAN Ratings

    [https://cpanratings.perl.org/d/QRCode-Base45](https://cpanratings.perl.org/d/QRCode-Base45)

- Search CPAN

    [https://metacpan.org/release/QRCode-Base45](https://metacpan.org/release/QRCode-Base45)

# ACKNOWLEDGEMENTS

# LICENSE AND COPYRIGHT

This software is copyright (c) 2021 by Jan "Yenya" Kasprzak.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
