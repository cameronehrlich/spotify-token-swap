This is an example token swap service written
as a Ruby/Sinatra service. This is required by
the iOS SDK to authenticate a user.

The service requires the Sinatra and
encrypted_strings gems be installed:

$ gem install sinatra encrypted_strings

To run the service, enter your client ID, client
secret and client callback URL below and run the
project.

$ ruby spotify_token_swap.rb

IMPORTANT: The example credentials will work for the
example apps, you should use your own in your real
environment. as these might change at any time.

Once the service is running, pass the public URI to
it (such as http://localhost:1234/swap if you run it
with default settings on your local machine) to the
token swap method in the iOS SDK:

NSURL *swapServiceURL = [NSURL urlWithString:@"http://localhost:1234/swap"];

-[SPAuth handleAuthCallbackWithTriggeredAuthURL:url
               tokenSwapServiceEndpointAtURL:swapServiceURL
                                    callback:callback];
