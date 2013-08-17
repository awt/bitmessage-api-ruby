## BitMessage API Ruby Wrapper

Thin API wrapper for the official BitMessage Python client.

## Usage

    require 'bitmessage/api_client.rb'

    api = BitMessage::ApiClient.new 'http://user:password@host:port/'

    api.add 3, 5

### Getting list of messages

    inbox = api.get_all_inbox_messages
    
    puts "You have #{inbox.count} messages:"

    inbox.each do |msg|
      puts "#{msg.msgid}  #{msg.from}  #{msg.subject}"
    end

### Sending a message


    to = "BM-orkCbppXWSqPpAxnz6jnfTZ2djb5pJKDb" # echo service
    from = api.list_addresses.first.address

    api.send_message to, from, "This is subject", "This is message"

## FAQ

Q: Does this cover 100% of the API?

A: Not yet.

