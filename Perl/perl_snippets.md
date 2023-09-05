## Perl 

### Hello World
```perl
print "Hello, World!\n";
```

### Variables
```perl
my $variable = "Value";
```

### User Input
```perl
print "Enter something: ";
my $input = <STDIN>;
chomp($input); # Remove newline
```

### Comments
```perl
# This is a comment
```

### If-Else
```perl
if ($condition) {
    # Code to execute if condition is true
} else {
    # Code to execute if condition is false
}
```

### For Loop
```perl
for my $i (1..10) {
    # Code to repeat 10 times
}
```

### While Loop
```perl
while ($condition) {
    # Code to execute while condition is true
}
```

### Arrays
```perl
my @array = (1, 2, 3);
```

### Hashes
```perl
my %hash = ('key1' => 'value1', 'key2' => 'value2');
```

### Subroutines
```perl
sub my_function {
    my ($arg1, $arg2) = @_;
    # Code to execute
}
```

### File Input/Output
```perl
open my $file, '<', 'filename.txt' or die "Couldn't open file: $!";
while (my $line = <$file>) {
    chomp($line);
    # Process each line
}
close $file;
```

### Regular Expressions
```perl
if ($string =~ /pattern/) {
    # Match found
}
```

### Splitting Strings
```perl
my @words = split(' ', $string);
```

### Joining Strings
```perl
my $new_string = join(', ', @array);
```

### Reading Command Line Arguments
```perl
my $arg1 = $ARGV[0];
```

### Getting the current date and time
```perl
use POSIX qw(strftime);
my $timestamp = strftime("%Y-%m-%d %H:%M:%S", localtime);
```

### Mathemathical Operations
```perl
my $result = $num1 + $num2;
```

### Sorting Arrays
```perl
my @sorted_array = sort @array;
```

### Removing Duplicates from Arrays
```perl
my %seen;
my @unique_array = grep { !$seen{$_}++ } @array;
```

### Checking if a file exists
```perl
if (-e 'filename.txt') {
    # File exists
}
```

### Creating a directory
```perl
mkdir 'new_directory';
```

### Deleting a file
```perl
unlink 'file_to_delete.txt';
```

### String concatenation
```perl
my $new_string = $string1 . $string2;
```

### String length
```perl
my $length = length($string);
```

### Reading Environment Variables
```perl
my $value = $ENV{'VAR_NAME'};
```

### Working with Dates
```perl
use Date::Calc qw(Today Add_Delta_Days);
my ($year, $month, $day) = Today();
my ($new_year, $new_month, $new_day) = Add_Delta_Days($year, $month, $day, 7);
```

### Executing external commands
```perl
my $output = `ls -l`;
```

### Random Number Generation
```perl
my $random_number = int(rand(100));
```

### Error Handling
```perl
eval {
    # Code that might throw an exception
};
if ($@) {
    # Handle the exception
}
```

### Using modules
```perl
use Module::Name;
```

### Sending email (with NET::SMTP)
```perl
use Net::SMTP;

my $smtp = Net::SMTP->new('smtp.example.com');
$smtp->mail('sender@example.com');
$smtp->to('recipient@example.com');
$smtp->data();
$smtp->datasend("Subject: Test Email\n");
$smtp->datasend("Hello, this is a test email.\n");
$smtp->dataend();
$smtp->quit;
```

### Working with JSON (JSON module)
```perl
use JSON;

my $json_text = '{"key":"value"}';
my $data = decode_json($json_text);
```

### Multiline Strings
```perl
my $multiline = <<"END_TEXT";
This is a
multiline string.
END_TEXT
```

### Fetching URL Content (with LWP::Simple)
```perl
use LWP::Simple;

my $content = get('https://example.com');
```

### URL Encoding/Dencoding
```perl
use URI::Escape;

my $encoded = uri_escape($string);
my $decoded = uri_unescape($encoded);
```

### Reading and writing CSV files (with Text::CSV)
```perl
use Text::CSV;

my $csv = Text::CSV->new({ binary => 1 });
open my $file, '<', 'data.csv' or die "Couldn't open file: $!";
while (my $row = $csv->getline($file)) {
    # Process each row
}
close $file;
```

### HTTP Server (with HTTP::Server::Simple)
```perl
use HTTP::Server::Simple;
use base qw(HTTP::Server::Simple::CGI);

sub handle_request {
    # Handle HTTP requests
}

my $server = MyWebServer->new;
$server->run();
```

### Calculating Hash digesets (with Digest::MD5)
```perl
use Digest::MD5;

my $digest = Digest::MD5->new;
$digest->add('data_to_hash');
my $hash = $digest->hexdigest;
```

### XML Parsing (with XML::LibXML)
```perl
use XML::LibXML;

my $parser = XML::LibXML->new;
my $doc = $parser->parse_file('data.xml');
```

### Database Interaction (with DBI)
```perl
use DBI;

my $dbh = DBI->connect('dbi:SQLite:dbname=database.db', '', '', { RaiseError => 1 });
my $sth = $dbh->prepare('SELECT * FROM table');
$sth->execute();
while (my $row = $sth->fetchrow_hashref()) {
    # Process database rows
}
$sth->finish();
$dbh->disconnect();
```

### Object Oriented Programming
```perl
package MyClass;

sub new {
    my ($class, $data) = @_;
    my $self = { data => $data };
    bless $self, $class;
    return $self;
}

sub get_data {
    my ($self) = @_;
    return $self->{data};
}

my $obj = MyClass->new('Some data');
print $obj->get_data();
```

### Exception Handling with Try::Tiny
```perl
use Try::Tiny;

try {
    # Code that might throw an exception
}
catch {
    warn "An error occurred: $_";
};
```

### Multithreading (with threads)
```perl
use threads;

my @threads;
foreach my $i (1..5) {
    push @threads, threads->create(\&subroutine, $i);
}
$_->join() foreach @threads;
```

### Using regular expression capture groups
```perl
my $string = "Date: 2023-09-05";
if ($string =~ /Date: (\d{4}-\d{2}-\d{2})/) {
    my $date = $1;
    print "Captured date: $date\n";
}
```

### File upload handler (with CGI)
```perl
use CGI;

my $cgi = CGI->new;
my $file = $cgi->upload('file_field_name');
if ($file) {
    my $filename = $cgi->param('file_field_name');
    open my $fh, '>', $filename or die "Couldn't open file: $!";
    while (my $chunk = $file->getline()) {
        print $fh $chunk;
    }
    close $fh;
}
```

### Using DBIx::Class for Database ORM
```perl
use DBIx::Class;

my $schema = DBIx::Class::Schema->connect('dbi:SQLite:dbname=database.db');
my $resultset = $schema->resultset('Table');
my $row = $resultset->find(1);
print $row->column_name;
```

### Working with DateTime Objects
```perl
use DateTime;

my $dt = DateTime->now;
$dt->add(days => 7);
print $dt->strftime("%Y-%m-%d %H:%M:%S");
```

### Sending HTTP Requests (with LWP::UserAgent)
```perl
use LWP::UserAgent;

my $ua = LWP::UserAgent->new;
my $response = $ua->get('https://example.com');
if ($response->is_success) {
    my $content = $response->content;
}
```

### Creating RESTful APIs (with Dancer2)
```perl
use Dancer2;

get '/api/resource/:id' => sub {
    my $id = route_parameters->get('id');
    # Fetch and return resource with ID $id
};

start;
```

### Parsing Command Line Arguments (with Getopt::Long)
```perl
use Getopt::Long;

my $input_file;
my $output_file;
GetOptions(
    'input=s'  => \$input_file,
    'output=s' => \$output_file,
);

print "Input file: $input_file\n";
print "Output file: $output_file\n";
```

### Template Processing (with Template::Toolkit)
```perl
use Template;

my $template = Template->new;
my $vars = { name => 'John', age => 30 };
$template->process('template.tt', $vars) || die $template->error();
```

### Asynchronous Programming (with Mojo::IOLoop)
```perl

use Mojo::IOLoop;

Mojo::IOLoop->delay(
    sub {
        my $delay = shift;
        # Asynchronous code here
        $delay->pass('Result');
    },
    sub {
        my ($delay, $result) = @_;
        # Handle the result
    },
)->wait;
```

### Handling Binary Data (with Encode)
```perl
use Encode;

my $encoded_data = encode_base64($binary_data);
my $decoded_data = decode_base64($encoded_data);
```

### Creating custom exception classes
```perl
package MyException;
use base 'Exception::Class';

package main;
use Try::Tiny;

try {
    MyException->throw("Custom exception message");
}
catch {
    if (MyException->caught($_)) {
        warn "Caught custom exception: $_\n";
    }
};
```

### Database Transactions (with DBIx::Class)
```perl
my $schema = DBIx::Class::Schema->connect('dbi:SQLite:dbname=database.db');
my $txn = $schema->txn_scope;
# Perform database operations within the transaction
$txn->commit; # or $txn->rollback;
```

### Using Moose for Object Oriented Programming
```perl
package MyClass;
use Moose;

has 'data' => (is => 'ro', isa => 'Str');

sub print_data {
    my ($self) = @_;
    print $self->data;
}

my $obj = MyClass->new(data => 'Some data');
$obj->print_data();
```

### Creating custom modules
```perl
package MyModule;

sub new {
    my ($class) = @_;
    my $self = {};
    bless $self, $class;
    return $self;
}

sub do_something {
    my ($self) = @_;
    # Code here
}

1; # Required for modules

# In another script
use MyModule;
my $module = MyModule->new();
$module->do_something();
```

### Parsing JSON with Error Handling (with JSON::MaybeXS)
```perl
use JSON::MaybeXS;

my $json_text = '{"key": "value"}';
my $data;
eval {
    $data = decode_json($json_text);
};
if ($@) {
    die "Error decoding JSON: $@";
}
```

### Web Scraping (with Mojo::UserAgent)
```perl
use Mojo::UserAgent;

my $ua = Mojo::UserAgent->new;
my $dom = $ua->get('https://example.com')->result->dom;
my $title = $dom->at('title')->text;
```

### Creating a RESTful API (with Mojolicious)
```perl
use Mojolicious::Lite;

get '/api/resource/:id' => sub {
    my $c = shift;
    my $id = $c->param('id');
    $c->render(json => { id => $id, data => 'Resource data' });
};

app->start;
```
