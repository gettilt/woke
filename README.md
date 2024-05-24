<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Woke
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
The world is becoming more aware of the inequalities, companies that are more liberal and progressive will win.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| AAPL | Apple has consistently shown commitment to diversity and inclusion in its hiring practices and product designs, making it a leader among progressive companies. | chat_gpt,claude,twitter,google |
| ADBE | Adobe's commitment to creativity and innovation goes hand in hand with its progressive stance on employee rights and diversity. | chat_gpt,claude,google |
| BEN | Franklin Resources has made strides in ESG (Environmental, Social, and Governance) investing, appealing to socially conscious investors. | chat_gpt |
| CRM | Salesforce is recognized for its culture of equality, philanthropy, and its commitment to the environment and social issues. | chat_gpt,claude,google |
| DIS | Disney promotes diversity and inclusion through its content and has made significant strides in representing various communities. | chat_gpt,claude,twitter,google |
| ETSY | Etsy's marketplace empowers small, often underrepresented, business owners and promotes sustainable goods. | chat_gpt,claude |
| GOOGL | Alphabet (Google's parent company) is known for its efforts in sustainability, digital inclusion, and the ethical use of AI. | chat_gpt,claude,google |
| INTU | Intuit invests in programs that promote diversity in tech and financial literacy, aligning with progressive values. | chat_gpt |
| LULU | Lululemon's emphasis on community and wellness aligns with progressive values, including sustainability and inclusion. | chat_gpt |
| MSFT | Microsoft's initiatives towards accessibility in technology and its strong stance on social issues align with a more liberal and progressive outlook. | chat_gpt,google |
| NFLX | Netflix's diverse content library promotes inclusivity and understanding, reflecting progressive values. | chat_gpt,claude,twitter |
| NKE | Nike's marketing and branding often align with progressive social causes, appealing to a global audience that values inclusivity. | chat_gpt,claude,google |
| SBUX | Starbucks has been at the forefront of corporate social responsibility, with progressive policies on employee education and social issues. | chat_gpt,claude,google |
| TSLA | Tesla's mission of sustainable energy aligns with progressive values towards environmental responsibility. | chat_gpt,twitter |
| AMZN |  | claude,twitter,google |
| LYFT |  | claude,twitter |
| MTCH |  | claude |
| PINS |  | claude |
| PYPL |  | claude,google |
| SHOP |  | claude |
| SNAP |  | claude |
| UBER |  | claude |
| BYND |  | twitter |
| META |  | twitter,google |
| PLTR |  | twitter |
| WBD |  | twitter |
| JNJ |  | google |
| MA |  | google |
| MAR |  | google |
| NVS |  | google |
| PGR |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/woke/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/woke" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
