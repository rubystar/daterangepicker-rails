# Date Range Picker For Twitter Bootstrap using Moment.js and Jquery

Everything is nicely documented [here](https://github.com/dangrossman/bootstrap-daterangepicker)

[LIVE DEMO HERE](http://www.dangrossman.info/2012/08/20/a-date-range-picker-for-twitter-bootstrap)
## Installation

Add this line to your application's Gemfile:

    gem 'daterangepicker-rails'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install daterangepicker-rails

## Usage

### Note: This plugin depends on Jquery, bootstrap, moment.js(which is already here).

    # Gemfile
    
    ...
    gem 'daterangepicker-rails'
    ...
    
    # app/assets/javascripts/application.js
    ...
    //= require moment
    //= require daterangepicker
    ...
    
    # app/assets/stylesheets/application.css
    # if you are using bootstrap 2
    ...
    *= require daterangepicker-bs2
    ...
    
    # if you are using bootstrap 3
    ...
    *= require daterangepicker-bs3
    ...
    
    
    # And in your JS file
    
    $(document).ready(function() {
      $('.date_range').daterangepicker({
        ranges: {
           'Today': [moment(), moment()],
           'Yesterday': [moment().subtract('days', 1), moment().subtract('days', 1)],
           'Last 7 Days': [moment().subtract('days', 6), moment()],
           'Last 30 Days': [moment().subtract('days', 29), moment()],
           'This Month': [moment().startOf('month'), moment().endOf('month')],
           'Last Month': [moment().subtract('month', 1).startOf('month'), moment().subtract('month', 1).endOf('month')]
        },
        locale: { cancelLabel: 'Clear' },
        format: 'YYYY-MM-DD',
        opens: 'left'
      });
    
      $('.date_range').on('cancel.daterangepicker', function(ev, picker) {
        $(this).val('');
      });
    });

## Contributing

1. Fork it ( https://github.com/[my-github-username]/daterangepicker-rails/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
