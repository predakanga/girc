<p align="center"><a href="https://pkg.go.dev/github.com/lrstanley/girc"><img width="270" src="http://i.imgur.com/DEnyrdB.png"></a></p>
<!-- template:begin:header -->
<!-- template:end:header -->

<!-- template:begin:toc -->
<!-- template:end:toc -->

## Features

- Focuses on simplicity, yet tries to still be flexible.
- Only requires [standard library packages](https://godoc.org/github.com/lrstanley/girc?imports)
- Event based triggering/responses ([example](https://godoc.org/github.com/lrstanley/girc#ex-package--Commands), and [CTCP too](https://godoc.org/github.com/lrstanley/girc#Commands.SendCTCP)!)
- [Documentation](https://godoc.org/github.com/lrstanley/girc) is _mostly_ complete.
- Support for a good portion of the [IRCv3 spec](http://ircv3.net/software/libraries.html).
  - SASL Auth (currently only `PLAIN` and `EXTERNAL` is support by default,
  however you can simply implement `SASLMech` yourself to support additional
  mechanisms.)
  - Message tags (things like `account-tag` on by default)
  - `account-notify`, `away-notify`, `chghost`, `extended-join`, etc -- all handled seemlessly ([cap.go](https://github.com/lrstanley/girc/blob/master/cap.go) for more info).
- Channel and user tracking. Easily find what users are in a channel, if a
  user is away, or if they are authenticated (if the server supports it!)
- Client state/capability tracking. Easy methods to access capability data ([LookupChannel](https://godoc.org/github.com/lrstanley/girc#Client.LookupChannel), [LookupUser](https://godoc.org/github.com/lrstanley/girc#Client.LookupUser), [GetServerOption (ISUPPORT)](https://godoc.org/github.com/lrstanley/girc#Client.GetServerOption), etc.)
- Built-in support for things you would commonly have to implement yourself.
  - Nick collision detection and prevention (also see [Config.HandleNickCollide](https://godoc.org/github.com/lrstanley/girc#Config).)
  - Event/message rate limiting.
  - Channel, nick, and user validation methods ([IsValidChannel](https://godoc.org/github.com/lrstanley/girc#IsValidChannel), [IsValidNick](https://godoc.org/github.com/lrstanley/girc#IsValidNick), etc.)
  - CTCP handling and auto-responses ([CTCP](https://godoc.org/github.com/lrstanley/girc#CTCP))
  - And more!

## Installing

    $ go get -u github.com/lrstanley/girc

## Examples

See [the examples](https://godoc.org/github.com/lrstanley/girc#example-package--Bare)
within the documentation for real-world usecases. Here are a few real-world
usecases/examples/projects which utilize girc:

| Project | Description |
| --- | --- |
| [nagios-check-ircd](https://github.com/lrstanley/nagios-check-ircd) | Nagios utility for monitoring the health of an ircd |
| [nagios-notify-irc](https://github.com/lrstanley/nagios-notify-irc) | Nagios utility for sending alerts to one or many channels/networks |
| [matterbridge](https://github.com/42wim/matterbridge) | bridge between mattermost, IRC, slack, discord (and many others) with REST API |

Working on a project and want to add it to the list? Submit a pull request!

## References

   * [IRCv3: Specification Docs](http://ircv3.net/irc/)
   * [IRCv3: Specification Repo](https://github.com/ircv3/ircv3-specifications)
   * [IRCv3 Capability Registry](http://ircv3.net/registry.html)
   * [IRCv3: WEBIRC](https://ircv3.net/specs/extensions/webirc.html)
   * [KiwiIRC: WEBIRC](https://kiwiirc.com/docs/webirc)
   * [ISUPPORT Specification Docs](http://www.irc.org/tech_docs/005.html) ([alternative 1](http://defs.ircdocs.horse/defs/isupport.html), [alternative 2](https://github.com/grawity/irc-docs/blob/master/client/RPL_ISUPPORT/draft-hardy-irc-isupport-00.txt), [relevant draft](http://www.irc.org/tech_docs/draft-brocklesby-irc-isupport-03.txt))
   * [IRC Numerics List](http://defs.ircdocs.horse/defs/numerics.html)
   * [Extended WHO (also known as WHOX)](https://github.com/quakenet/snircd/blob/master/doc/readme.who)
   * [RFC1459: Internet Relay Chat Protocol](https://tools.ietf.org/html/rfc1459)
   * [RFC2812: Internet Relay Chat: Client Protocol](https://tools.ietf.org/html/rfc2812)
   * [RFC2813: Internet Relay Chat: Server Protocol](https://tools.ietf.org/html/rfc2813)
   * [RFC7194: Default Port for Internet Relay Chat (IRC) via TLS/SSL](https://tools.ietf.org/html/rfc7194)
   * [RFC4422: Simple Authentication and Security Layer](https://tools.ietf.org/html/rfc4422) ([SASL EXTERNAL](https://tools.ietf.org/html/rfc4422#appendix-A))
   * [RFC4616: The PLAIN SASL Mechanism](https://tools.ietf.org/html/rfc4616)


<!-- template:begin:support -->
<!-- template:end:support -->

<!-- template:begin:contributing -->
<!-- template:end:contributing -->

<!-- template:begin:license -->
<!-- template:end:license -->
girc artwork licensed under [CC 3.0](http://creativecommons.org/licenses/by/3.0/)
based on Renee French under Creative Commons 3.0 Attributions.
