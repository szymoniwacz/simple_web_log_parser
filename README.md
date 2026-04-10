# Web Log Parser

## About

This project was created as a coding challenge to parse a web server log file and provide statistics on total and unique page views using Ruby. It demonstrates Command Line Interface (CLI) scripting, Object-Oriented Programming, and unit testing best practices.

## Project Status

:white_check_mark: Reference implementation – ready and correct, not under active development.

## Features

- Counts total page views per page.
- Counts unique page views based on unique IP addresses.
- Handles invalid log entries gracefully by skipping lines missing the page or IP.
- Outputs page views sorted by the number of views and, in the case of ties, alphabetically by page name.

## Requirements

- Ruby 2.6.0 or later
- RSpec (for running tests)

## Installation

1. Clone the repository:

```
git clone https://github.com/szymoniwacz/web-log-parser.git
cd ruby_app
```

2. Install dependencies:

```
bundle install
```

## Usage

1. Prepare a log file in the following format:

```
/home 192.168.0.1
/index 192.168.0.2
/about 192.168.0.3
/home 192.168.0.4
```

2. Run the parser from the command line:

```
ruby parser.rb webserver.log
```

3. Example output:

```
Page views:
/home 10 visits
/index 5 visits

Unique page views:
/home 5 unique views
/index 3 unique views
```

## Running Tests

1. Ensure you have RSpec installed:

```
bundle install
```

2. Run the tests:

```
rspec spec/parser_service_spec.rb
```

3. The tests will validate the following:
   - The script correctly parses total page views.
   - The script correctly parses unique page views.
   - The script handles invalid log entries (missing page or IP).
   - Sorting of pages with tied view counts works correctly.

## Log File Format

The log file should follow the format:
<page> <IP_address>

Example:

```
/home 192.168.0.1
/index 192.168.0.2
/about/2 192.168.0.3
```

Each line in the log file represents a visit to a page from an IP address. The parser will count how many times each page has been visited and how many unique IP addresses visited each page.

## Project Structure

- `parser.rb`: The executable script that runs the ParserService.
- `parser_service.rb`: The main ParserService class.
- `spec/`: Contains RSpec tests for the ParserService.
- `spec/fixtures/`: Sample log files used in tests.

## License

This project is licensed under the MIT License.
