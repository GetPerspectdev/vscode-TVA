# Perspect for Visual Studio Code

[Perspect][perspect] is an open source VS Code plugin for the Perspect platform. Gain real-time insight into your contributions and impact of your work. Optimize developer experience and reward high-performers.

## Installation

1. Press `F1` or `⌘ + Shift + P` and type `install`. Pick `Extensions: Install Extension`.

   ![type install](./images/type-install.png)

2. Type `perspect` and hit `enter`.
 
3. Enter your [api key][api key], then press `enter`.

   > (If you’re not prompted, press `F1` or `⌘ + Shift + P` then type `Perspect API Key`.)

4. Use VSCode normally and your coding activity will be displayed on your [Perspect dashboard](https://app.perspect.xyz)

## Usage

Visit [https://app.perspect.xyz](https://app.perspect.xyz) to see your coding activity.

![Project Overview](https://app.perspect.xyz/referralEmailScreenshot.png)

## Tech

Perspect uses the incredible work done by Alan Hamlet the wakatime team!

## Configuring

VS Code specific settings are available from `⌘ + Shift + P`, then typing `perspect`.

For example, to hide today's coding activity in your status bar:

Press `⌘ + Shift + P` then set `Perspect: Status Bar Coding Activity` to `false`.

Extension settings are stored in the INI file at `$HOME/.wakatime.cfg`.

More information can be found from [wakatime-cli][wakatime-cli configs].

If using an online IDE like [gitpods](https://gitpod.io/), add your [api key][api key] to global ENV key `PERSPECT_API_KEY`.

Notes:

1. `$HOME` defaults to `$HOME`
1. To disable the extension at startup add `disabled=true` to your config, this operation can also be performed by pressing `⌘ + Shift + P` and selecting `Perspect: Disable`.

## Troubleshooting

First, turn on debug mode:

1. Press `F1` or `⌘ + Shift + P`
2. Type `> Perspect: Debug`, and press `Enter`.
3. Select `true`, then press `Enter`.

Next, open your Developer Console to view logs and errors:

`Help → Toggle Developer Tools`

Errors outside the scope of vscode-perspect go to `$HOME/.wakatime/wakatime.log` from [wakatime-cli][wakatime-cli help].

If your error message contains "won't send heartbeat due to backoff" then delete your `~/.wakatime/wakatime-internal.cfg` file to trigger an API connection so we can see the real error message.

The [How to Debug Plugins][how to debug] guide shows how to check when coding activity was last received from your editor using the [Plugins Status Page][plugins status page].

**Microsoft Windows Only:** Using Perspect behind a corporate proxy? Try enabling your Windows Root Certs inside VS Code with the [win-ca][winca] extension:
Press `Ctrl + Shift + X`, search for `win-ca`, press `Install`.

For more general troubleshooting info, see the [wakatime-cli Troubleshooting Section][wakatime-cli help].

### SSH configuration

If you're connected to a remote host using the [ssh extension](https://code.visualstudio.com/docs/remote/ssh) you might want to force WakaTime to run locally instead on the server. This configuration is needed when the server you connect is shared among other people. Please follow [this](https://code.visualstudio.com/docs/remote/ssh#_advanced-forcing-an-extension-to-run-locally-remotely) guide.

## Uninstalling

1. Click the Extensions sidebar item in VS Code.

2. Type `perspect` and hit enter.

3. Click the settings icon next to Perspect, then click Uninstall.

4. Delete the `~/.wakatime*` files in your home directory, unless you’re still using Perspect with another IDE.

## Contributing

Pull requests, bug reports, and feature requests are welcome!
Please search [existing issues][issues] before creating a new one.

To run from source:

1. `git clone git@github.com:GetPerspectdev/vscode-TVA.git`
2. `cd vscode-TVA`
3. `npm install`
4. `npm run watch`
5. Install the extension from the marketplace
6. Then symlink `~/.vscode/extensions/perspect.vscode-perspect-*/dist/extension.js` to `./dist/extension.js`

Or to run the web version from source:

1. `git clone git@github.com:GetPerspectdev/vscode-TVA.git`
2. `cd vscode-TVA`
3. `npm install`
4. `npm run compile`
5. `npm run open-in-browser`
6. Go to [localhost:3000](http://localhost:3000/) in your web browser

Many thanks to all [contributors](AUTHORS)!

Made with :heart: by the [Perspect Team][about].

[perspect]: https://www.perspect.xyz
[api key]: https://app.perspect.xyz/account
[wakatime-cli help]: https://github.com/wakatime/wakatime-cli/blob/develop/TROUBLESHOOTING.md
[wakatime-cli configs]: https://github.com/wakatime/wakatime-cli/blob/develop/USAGE.md
[how to debug]: https://wakatime.com/faq#debug-plugins
[plugins status page]: https://app.perspect.xyz/sources
[winca]: https://github.com/ukoloff/win-ca/tree/master/vscode
[issues]: https://github.com/GetPerspectdev/vscode-TVA/issues
[about]: https://www.perspect.xyz
