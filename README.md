# NAME

Plack::App::Catmandu::Bag - Plack application that wraps a REST API around a Catmandu::Bag

# SYNOPSIS

    use Catmandu;
    use Plack::Builder;
    use Plack::App::Catmandu::Bag;

    Catmandu->define_store('library',
        MongoDB => (bags => {books => {plugins => ['Versioning']}}));

    builder {
        mount '/api/books' => Plack::App::Catmandu::Bag->new(
            store => 'library',
            bag => 'books',
        );
    };

# AUTHOR

Nicolas Steenlant <nicolas.steenlant@ugent.be>

# COPYRIGHT

Copyright 2017- Nicolas Steenlant

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO
