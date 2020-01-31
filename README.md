# NAME

SVG::Barcode::QRCode - Generator for SVG based QR Codes

# SYNOPSIS

    use SVG::Barcode::QRCode;

    my $qrcode = SVG::Barcode::QRCode->new;
    my $svg    = $qrcode->plot('https://perldoc.pl');

    $qrcode->level;         # M
    $qrcode->dotsize;       # 1
    $qrcode->version;       # 0
                            # from SVG::Barcode:
    $qrcode->foreground;    # black
    $qrcode->background;    # white
    $qrcode->margin;        # 2
    $qrcode->id;
    $qrcode->class;
    $qrcode->width;
    $qrcode->height;
    $qrcode->scale;

    my %params = (
      level  => 'H',
      margin => 4,
    );
    $qrcode = SVG::Barcode::QRCode->new(%params);

    # use as function
    use SVG::Barcode::QRCode 'plot_qrcode';

    $svg = plot_qrcode('https://perldoc.pl', %params);

# DESCRIPTION

[SVG::Barcode::QRCode](https://metacpan.org/pod/SVG%3A%3ABarcode%3A%3AQRCode) is a generator for SVG based QR Codes.

# FUNCTIONS

## plot\_qrcode

    use SVG::Barcode::QRCode 'plot_qrcode';

    $svg = plot_qrcode($text, %params);

Returns a QR Code using the provided text and parameters.

# CONSTRUCTOR

## new

    $qrcode = SVG::Barcode::QRCode->new;            # create with defaults
    $qrcode = SVG::Barcode::QRCode->new(%params);

Creates a new QR Code plotter. Inherited from [SVG::Barcode](https://metacpan.org/pod/SVG%3A%3ABarcode#new).

# METHODS

## plot

    $svg = $qrcode->plot($text);

Creates a SVG code. Inherited from [SVG::Barcode](https://metacpan.org/pod/SVG%3A%3ABarcode#plot).

# PARAMETERS

Inherited from [SVG::Barcode](https://metacpan.org/pod/SVG%3A%3ABarcode):
[background](https://metacpan.org/pod/SVG%3A%3ABarcode#background),
[class](https://metacpan.org/pod/SVG%3A%3ABarcode#class),
[foreground](https://metacpan.org/pod/SVG%3A%3ABarcode#foreground),
[height](https://metacpan.org/pod/SVG%3A%3ABarcode#height),
[id](https://metacpan.org/pod/SVG%3A%3ABarcode#id),
[margin](https://metacpan.org/pod/SVG%3A%3ABarcode#margin),
[scale](https://metacpan.org/pod/SVG%3A%3ABarcode#scale),
[width](https://metacpan.org/pod/SVG%3A%3ABarcode#width).

## dotsize

    $value  = $qrcode->dotsize;
    $qrcode = $qrcode->dotsize($newvalue);
    $qrcode = $qrcode->dotsize('');          # 1

Getter and setter for the size of the dots. Default `1`.

## level

    $value  = $qrcode->level;
    $qrcode = $qrcode->level($newvalue);
    $qrcode = $qrcode->level('');          # M

Getter and setter for the error correction level. One of one of `L` (low), `M` (medium), `Q`
(quartile), `H` (high). Default `M`.

## version

    $value  = $qrcode->version;
    $qrcode = $qrcode->version($newvalue);
    $qrcode = $qrcode->version('');          # 0

Getter and setter for the symbol version. From `1` to `40`. `0` will adapt the version to the
required capacity. Default `0`.

# AUTHOR & COPYRIGHT

© 2019–2020 by Tekki (Rolf Stöckli).

This program is free software, you can redistribute it and/or modify it under the terms of the
Artistic License version 2.0.

# SEE ALSO

[SVG::Barcode](https://metacpan.org/pod/SVG%3A%3ABarcode), [Text::QRCode](https://metacpan.org/pod/Text%3A%3AQRCode).
