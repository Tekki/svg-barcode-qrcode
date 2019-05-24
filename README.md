# NAME

SVG::Barcode::QRCode - Generator for SVG based QR Codes

# SYNOPSIS

    use SVG::Barcode::QRCode;

    my %params = (    # defaults
      background => 'white',
      foreground => 'black',
      level      => 'M',
      margin     => 10,
      size       => 5,
      version    => 0,
    );
    my $qrcode = SVG::Barcode::QRCode->new(\%params);
    my $svg    = $qrcode->plot('https://perldoc.pl');
    my $svg2   = $qrcode->param(foreground => 'red')->plot('https://perldoc.pl');

    # use as function
    use SVG::Barcode::QRCode 'plot_qrcode';

    my $svg = plot_qrcode('https://perldoc.pl', \%params);

# DESCRIPTION

[SVG::Barcode::QRCode](https://metacpan.org/pod/SVG::Barcode::QRCode) is a generator for SVG based QR Codes.

# FUNCTIONS

## plot\_qrcode

    use SVG::Barcode::QRCode 'plot_qrcode';

    my $svg = plot_qrcode($text, \%params);

Returns a QR Code using the provided text and parameters.

# CONSTRUCTOR

## new

    $qrcode = SVG::Barcode::QRCode->new(\%params);
    $qrcode = SVG::Barcode::QRCode->new;             # create with defaults

Creates a new QR Code plotter. Inherited from ["new" in SVG::Barcode](https://metacpan.org/pod/SVG::Barcode#new).

Accepted parameters are:

- background

    Color of the background. Default `'white'`.

- foreground

    Color of the dots. Default `'black'`.

- level

    Error correction level, one of `'L'` (low), `'M'` (medium), `'Q'` (quartile), `'H'` (high). Default `'M'`.

- margin

    Margin around the code. Default `10`.

- size

    Size of the dots. Default `5`.

- version

    Symbol version from `1` to `40`. `0` will adapt the version to the required capacity. Default `0`.

# METHODS

## param

Getter and setter for the parameters. Inherited from ["param" in SVG::Barcode](https://metacpan.org/pod/SVG::Barcode#param).

## plot

Creates a SVG code. Inherited from ["plot" in SVG::Barcode](https://metacpan.org/pod/SVG::Barcode#plot).

# SEE ALSO

[SVG::Barcode](https://metacpan.org/pod/SVG::Barcode), [Text::QRCode](https://metacpan.org/pod/Text::QRCode).

# AUTHOR & COPYRIGHT

© 2019 by Tekki (Rolf Stöckli).

This program is free software, you can redistribute it and/or modify it under the terms of the Artistic License version 2.0.
