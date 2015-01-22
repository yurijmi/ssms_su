# ssms_su

Sending SMS via SSMS.SU API. For more details see http://user.ssms.su/api_manual/

## Installation

Add this line to your application's Gemfile:

    gem 'ssms_su'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install ssms_su

## Usage

In the begining, you need to [register](http://user.ssms.su/) for sending SMS through ssms_su gateway.

There are two ways for sending your SMS.

The first - it's sending a SMS to one recipient. To do this, use:

```
SmsApi.push_msg_nologin('your@email.com', 'your_password', 'recipient_phone', 'sms_text', params)
```

here `recipient_phone` - is a phone number in format '7xxxyyyzzzz' and `params` - additional params that you can see in [documentation].

The second way - it's sending multiple SMS to multiple recipients.

```
SmsApi.login('your@email.com', 'your_password')
recipient_phones_str_arr.each do |recipient_phone|
  SmsApi.push_msg(recipient_phone, 'sms_text', params)
end
```

here `recipient_phones_str_arr` - it's array that consist phone numbers as strings in format that represented above.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request