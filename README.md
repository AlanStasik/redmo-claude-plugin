# RedMo for Claude

[RedMo](https://redmo.xyz) is a free live quiz platform. A host puts a quiz on
a big screen, and everyone in the room joins from their phone with a PIN and
plays along.

This plugin lets Claude build those quizzes in your own RedMo account. Describe
a topic, or paste your notes or a lesson plan, and Claude writes the
questions, picks a fitting question type for each one, shows them to you, and
saves the quiz. You host it from the link Claude gives you.

## What is in it

- **The RedMo connector** (`.mcp.json`): RedMo's remote MCP server at
  `https://redmo.xyz/mcp`. Nothing runs on your machine.
- **The `build-a-quiz` skill**: how to write questions that work when they are
  read from the back of a room, which question type suits which content, and
  how to edit a quiz one slide at a time without overwriting your own changes.

## What Claude can do with it

- Create a quiz with multiple choice, true or false, pick the set, type the
  answer, slider, pin on the picture, put in order and picture answers; polls,
  scales, word clouds, open-ended questions and brainstorms; and title, bullet
  point, quote and media slides.
- Read your quizzes and change them one slide at a time: edit, insert, move or
  remove a slide by its id, leaving the rest alone.
- Find pictures in a stock photo library, show them to you so you choose, and
  attach the one you pick.
- Publish a draft when you ask.

It does not start or run a live game, see players or results, delete whole
quizzes, or reach any account but yours.

## Connecting

Install the plugin, then connect RedMo when Claude asks. A RedMo page opens:
sign in (an emailed code, or Google) and press **Approve**. There is no key to
copy. You can disconnect at any time in RedMo under **Settings > Connect your
AI**.

Without the plugin you can add the connector on its own: in Claude, **Settings
> Connectors > Add custom connector**, URL `https://redmo.xyz/mcp`. Full setup
for every client: https://redmo.xyz/ai

## What it sends, and where

- Every request goes to RedMo's server, `https://redmo.xyz/mcp`, over HTTPS,
  signed with the OAuth token you approved. It carries the quiz content Claude
  writes or reads: titles, questions, answers, timings and picture URLs.
- Picture searches go to the same server, which looks them up in the
  [Pexels](https://www.pexels.com) library and returns the results. When you
  choose one, RedMo copies it into its own storage so the quiz keeps working.
- The plugin sends nothing else. It runs no local code, reads no files on your
  machine, and does not see your conversation beyond what each tool call
  contains.

## Privacy

RedMo stores the quizzes in your account and the sign-in it needs to keep you
connected. It does not sell your data or share it with advertisers, and you
can ask for your account and its content to be deleted at legal@redmo.xyz.
The full policy, including what is collected: https://redmo.xyz/terms

## Support

https://redmo.xyz/contact

## License

MIT. See [LICENSE](LICENSE). The license covers this plugin's files; the
RedMo service is used under its own terms.
