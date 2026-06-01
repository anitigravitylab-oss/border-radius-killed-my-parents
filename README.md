# border-radius-killed-my-parents

> AIは、今日も何の罪もない四角形に `border-radius: 9999px` を与えている。  
> 私の両親も、そうして丸められた。

`border-radius-killed-my-parents` は、AIが生成したフロントエンドにありがちな「とりあえず丸くしておけば今っぽいでしょ？」という思想を矯正するためのデザインスキルです。

これは個人的な復讐です。

私は幼い頃、過剰な `border-radius` によって両親を失いました。

詳しい経緯は話せません。  
ただ、あの日から私は、意味もなく丸められたUIを見るたびに、静かに拳を握るようになりました。

名前はふざけていません。  
思想もふざけていません。  
ふざけているのは、すべての要素に `rounded-full` を付けるAIの方です。

## これは何？

AIが作るWeb UIには、独特の癖があります。

たとえば：

- 何でも角丸にする
- 何でもカードに入れる
- 何でもピル型バッジにする
- 何でもグラデーションで誤魔化す
- 何でも「直感的」「シームレス」「パワフル」と言い出す
- ユーザー価値より先に技術スタックを自慢する
- 日本語サイトなのに、フォントだけ英語圏SaaSの顔をしている
- 見た目は整っているのに、何をするサービスなのか分からない
- なんか全体的に、NotionとSaaSテンプレートとChatGPTの夢の残骸みたいになる

このスキルは、そういうAI生成UI特有の「それっぽさの死骸」を見つけて、もう少し人間が作ったものに近づけるためのものです。

言い換えると、これはAIが量産する「丸くて、薄くて、やさしそうで、何も言っていないUI」への対抗手段です。

## なぜ作ったのか

これは個人的な復讐です。

私は幼い頃、過剰な `border-radius` によって両親を失いました。

事件の詳細は伏せます。  
ただひとつ言えるのは、そこには丸すぎるカード、意味のない影、そして `rounded-full` がありました。

それ以来、私はAI生成UIを見るたびに同じ気配を感じます。

ボタンも丸い。  
カードも丸い。  
バッジも丸い。  
入力欄も丸い。  
アイコンの背景も丸い。  
意味のない装飾も丸い。  
存在理由の分からないCTAも丸い。

どうしてそんなに丸くしたがるのか。

まだ足りないのでしょうか。  
私の両親だけでは。

丸ければ優しいわけではありません。  
角が取れていれば洗練されているわけでもありません。  
`rounded-2xl` を付けた瞬間にプロダクトの価値が上がるわけでもありません。

これは角丸そのものとの戦いではありません。

これは、**意味のない丸さ**との戦いです。

## 思想

四角形にカウンセリングは必要ありません。

テキストをピル型バッジに閉じ込めても、内容が濃くなるわけではありません。

カードを入れ子にしても、情報設計が上手くなるわけではありません。

グラデーションを敷いても、言葉の中身は増えません。

「Reactで作りました」は、ユーザーにとってはだいたいどうでもいいです。

「高速・直感的・シームレス」は、何も言っていないのに言った気になるための三種の神器です。

「あなたの〇〇を次のレベルへ」は、何も思いつかなかった時にAIが最後に吐く白旗です。

良いUIは、  
「私は40,000個のSaaSランディングページを学習したAIが、深夜2時に生成しました」  
という顔をしていない方がいい。

そして何より、良いUIはユーザーに向いているべきです。

AIに褒められるためでも、ポートフォリオをSaaSっぽく見せるためでも、謎の3カード構成を成立させるためでもありません。

UIは、ユーザーのためにあります。  
`rounded-full` の就職先ではありません。

## 何を直すのか

このスキルは、プロジェクト内のAIっぽいデザインパターンを見つけます。

ただし、すべての角丸を絶滅させるわけではありません。

必要な角丸は残します。  
不要な角丸は減らします。  
意味のない装飾は削ります。  
何も説明していない抽象語は疑います。  
謎のバッジ群は取り調べます。  
SaaSっぽいだけの空気を抜きます。

犯人は角丸ではありません。  
犯人は、何も考えずに角丸を使うことです。

たとえば：

```css
/* before */
border-radius: 24px;

/* after */
border-radius: 8px;
```

```html
<!-- before -->
<span class="badge rounded-full">React</span>
<span class="badge rounded-full">API</span>
<span class="badge rounded-full">Full-stack</span>
<span class="badge rounded-full">Modern</span>
<span class="badge rounded-full">Seamless</span>

<!-- after -->
<p>このサービスで何ができるのかを、ユーザーに伝える。</p>
```

あるいは：

```html
<!-- before -->
<section class="rounded-3xl shadow-xl bg-white p-10">
  <div class="rounded-2xl shadow-md p-8">
    <div class="rounded-full bg-blue-100 px-4 py-2">Innovative</div>
    <h2>あなたの体験を次のレベルへ</h2>
  </div>
</section>

<!-- after -->
<section>
  <h2>何を解決するのかを、まず書く。</h2>
</section>
```

## このプロジェクトが信じていること

* `rounded-full` は人格ではない
* `rounded-2xl` は免罪符ではない
* ピル型バッジは情報設計ではない
* 技術スタックは自己紹介ではなく、裏方で働いていてほしい
* 「シームレス」は、説明に困ったAIがよく出す煙幕である
* カードを増やしても、構造化したことにはならない
* グラデーションは、内容の薄さを隠す毛布ではない
* 日本語サイトには日本語フォントの事情がある
* すべてを強調すると、何も強調されない
* それっぽいUIより、意味が伝わるUIの方が強い
* AIっぽさは、余白・角丸・抽象語・謎バッジに出る
* 角丸は悪ではないが、無罪でもない
* デザインとは、CSSプロパティの人気投票ではない

## 使いどころ

AIに作らせたフロントエンドを見て、こう思ったときに使ってください。

> なんで全部こんなに丸いんだ？

または：

> なんで意味のないバッジが17個も並んでるんだ？

または：

> これはポートフォリオなのか、存在しないB2B SaaSのLPなのか？

または：

> このUI、何も悪いことはしていないのに、なぜか腹が立つ。

または：

> なぜこのプロフィールページは、資金調達前のSaaS企業みたいな顔をしているのか？

そういうとき、このスキルは役に立つかもしれません。

## 対象となる症状

このような症状が見られる場合、AI生成UI角丸過多症候群の疑いがあります。

* 全体的に丸い
* 何かあるたびにカードが出てくる
* バッジが多い
* 「革新的」「直感的」「効率的」が頻出する
* 画面は綺麗なのに、印象に残らない
* 余白が妙に広い
* セクションごとに同じようなカードが3枚並ぶ
* CTAボタンがやたら優しそう
* 日本語なのに、英語SaaSテンプレートを翻訳した匂いがする
* どのページも「AIにちゃんと作ってもらいました」という顔をしている
* 内容より先に雰囲気が来る
* 雰囲気のわりに、何も起きていない

重症化すると、以下のような症状が出ます。

> すべての要素が白いカードの中に入り、
> すべてのカードが角丸になり、
> すべての角丸が影を持ち、
> すべての文章が「あなたの〇〇を次のレベルへ」で終わる。

末期症状では、トップページに以下の3カードが出現します。

* Fast
* Intuitive
* Powerful

そして誰も、何がFastで、何がIntuitiveで、何がPowerfulなのかを説明できません。

## 注意

このスキルを使うと、以下のような副作用が起きる可能性があります。

* ピル型バッジが減る
* 角丸が控えめになる
* 日本語が読みやすくなる
* 謎のSaaS感が薄まる
* 「なんか今っぽい」が減る
* 「ちゃんと意味がある」が増える
* AI生成UIへの怒りが少しだけ成仏する
* 角のある人生を受け入れられるようになる
* デザインをした気になる時間が減る
* 本当に何を伝えるべきか考える時間が増える

これは一見つらいことです。
でも、それがデザインです。

## よくある誤解

### 角丸は全部ダメなの？

違います。

角丸そのものは悪くありません。
ただし、何も考えずに付けられた角丸は疑われるべきです。

角丸には役割があります。
柔らかさを出す。
階層を作る。
触れる要素だと示す。
視線の流れを整える。

しかし、AI生成UIではしばしば、角丸は役割ではなく癖になります。

癖になった角丸は、もうデザインではありません。
ただの反射です。

### カードUIは全部ダメなの？

違います。

カードUIは便利です。
情報のまとまりを表現するには有効です。

ただし、何でもカードに入れると、すべてが同じ重要度に見えます。

そして最終的に、ページ全体が「カードを並べるために存在するページ」になります。

ユーザーはカードを見に来たわけではありません。
情報を見に来ています。

### AIにUIを作らせるのはダメなの？

違います。

AIは便利です。
速いです。
たたき台を作るには強いです。

ただし、AIが出してきたものをそのまま信じると、だいたい丸くなります。

AIは平均値を出すのが得意です。
そして現代の平均的なWeb UIは、少し丸すぎます。

## 最後に

このスキルは、AI生成UIを少しだけ人間らしくするためのものです。

角丸を減らし、謎バッジを消し、抽象語を疑い、SaaSテンプレート臭を薄める。

しかし、残念なお知らせがあります。

ここまでやっても、結局いちばん良いのは、
**最初から人間がちゃんと考えて作ることです。**

AIに作らせて、AIっぽさを消すためにまたAIを使う。

私たちは今、かなり遠回りな方法で、
「人間がデザインする」という地点に戻ろうとしています。

とても先進的です。
ほとんど縄文時代です。

## License

MIT

このプロジェクトの制作中、四角形は傷つけられていません。
ただし、いくつかのピル型バッジは静かに処理されました。

---

# English

# border-radius-killed-my-parents

> AI keeps giving innocent rectangles `border-radius: 9999px`.
> My parents were rounded the same way.

`border-radius-killed-my-parents` is a design skill for correcting one of the most suspicious habits of AI-generated frontend code:

> "Just round everything and call it modern."

This is personal.

I lost my parents to excessive `border-radius`.

I cannot discuss the details.
But ever since that day, every meaningless pill badge, every soft card, every aggressively friendly CTA has felt like evidence.

The name is not a joke.
The philosophy is not a joke.
The joke is AI putting `rounded-full` on everything and calling it design.

## What is this?

AI-generated web UI has a very specific smell.

For example:

* everything has rounded corners
* everything is inside a card
* everything becomes a pill badge
* gradients are used as emotional support
* every product is "intuitive", "seamless", and "powerful"
* the tech stack appears before the user benefit
* Japanese websites somehow look like translated English SaaS templates
* the UI looks clean, but nobody knows what the product actually does
* the whole thing feels like the remains of Notion, a SaaS template, and ChatGPT having the same dream

This skill exists to detect that AI-generated frontend smell and make the design feel a little more like something a human actually thought about.

In other words, this is a countermeasure against UI that is round, soft, friendly-looking, and completely empty.

## Why?

This is personal.

I lost my parents to excessive `border-radius`.

I cannot disclose the details.
All I can say is that there were overly soft cards, meaningless shadows, and `rounded-full`.

Since then, every AI-generated frontend gives me the same feeling.

The buttons are round.
The cards are round.
The badges are round.
The inputs are round.
The icon backgrounds are round.
The meaningless decorations are round.
Even the CTA with no clear reason to exist is round.

Why does AI want everything to be so round?

Was my family not enough?

Round does not automatically mean friendly.
Smooth corners do not automatically mean refined.
Adding `rounded-2xl` does not increase product value.

This is not a war against rounded corners.

This is a war against **meaningless roundness**.

## Philosophy

Rectangles do not need therapy.

Putting text inside a pill badge does not make it more meaningful.

Nesting cards inside cards does not count as information architecture.

A gradient does not add substance to empty copy.

"Built with React" is usually not a user benefit.

"Fast, intuitive, and seamless" is the holy trinity of saying nothing while sounding like you said something.

"Take your ___ to the next level" is the white flag AI waves when it has run out of ideas.

Good UI should not look like:

> "I was generated at 2 a.m. by an AI trained on 40,000 SaaS landing pages."

Most importantly, good UI should be directed at users.

Not at impressing AI.
Not at making a portfolio look like a SaaS company.
Not at justifying yet another three-card layout.

UI exists for users.
It is not an employment program for `rounded-full`.

## What does it fix?

This skill looks for AI-ish design patterns inside a project.

It does not blindly destroy every rounded corner.

It keeps useful rounded corners.
It reduces unnecessary rounded corners.
It removes meaningless decoration.
It questions vague abstract copy.
It interrogates suspicious badge clusters.
It lets the fake SaaS air out of the room.

The criminal is not border radius.
The criminal is using border radius without thinking.

For example:

```css
/* before */
border-radius: 24px;

/* after */
border-radius: 8px;
```

```html
<!-- before -->
<span class="badge rounded-full">React</span>
<span class="badge rounded-full">API</span>
<span class="badge rounded-full">Full-stack</span>
<span class="badge rounded-full">Modern</span>
<span class="badge rounded-full">Seamless</span>

<!-- after -->
<p>Explain what the product actually helps users do.</p>
```

Or:

```html
<!-- before -->
<section class="rounded-3xl shadow-xl bg-white p-10">
  <div class="rounded-2xl shadow-md p-8">
    <div class="rounded-full bg-blue-100 px-4 py-2">Innovative</div>
    <h2>Take your experience to the next level</h2>
  </div>
</section>

<!-- after -->
<section>
  <h2>Start by explaining what problem this solves.</h2>
</section>
```

## Things this project believes

* `rounded-full` is not a personality
* `rounded-2xl` is not a get-out-of-design-free card
* pill badges are not information architecture
* the tech stack should usually stay backstage
* "seamless" is smoke released by AI when it runs out of meaning
* adding more cards does not mean you structured the content
* gradients are not blankets for thin ideas
* Japanese websites need Japanese typography considerations
* when everything is emphasized, nothing is emphasized
* meaningful UI is stronger than merely modern-looking UI
* AI-ness often appears in spacing, border radius, vague copy, and mysterious badges
* rounded corners are not evil, but they are not innocent either
* design is not a popularity contest between CSS properties

## When to use it

Use this when you look at an AI-generated frontend and think:

> Why is everything so round?

Or:

> Why are there 17 meaningless badges?

Or:

> Is this a portfolio, or a landing page for a B2B SaaS product that does not exist?

Or:

> This UI has done nothing wrong, yet somehow it offends me.

Or:

> Why does this profile page look like a pre-seed SaaS startup?

In those moments, this skill may help.

## Symptoms

Your project may be suffering from AI-generated rounded-corner syndrome if:

* everything is round
* every section has cards
* there are too many badges
* "innovative", "intuitive", and "efficient" appear too often
* the page is pretty but forgettable
* the spacing feels suspiciously generous
* every section contains the same three-card layout
* the CTA button looks aggressively friendly
* the Japanese copy smells like an English SaaS template passed through translation
* every page has the face of something that was "properly generated by AI"
* the mood arrives before the meaning
* despite all the atmosphere, nothing actually happens

In severe cases:

> Every element enters a white card,
> every card gets rounded corners,
> every rounded corner gets a shadow,
> and every sentence ends with "take your ___ to the next level."

In terminal cases, the homepage produces the following three cards:

* Fast
* Intuitive
* Powerful

And nobody can explain what is fast, what is intuitive, or what is powerful.

## Warning

Using this skill may cause:

* fewer pill badges
* less aggressive rounded corners
* more readable Japanese
* reduced fake SaaS energy
* less "modern-looking"
* more "actually meaningful"
* mild emotional recovery from AI-generated frontend trauma
* acceptance of a life with corners
* less time pretending to design
* more time deciding what actually needs to be communicated

This may be painful.

That pain is called design.

## Common misconceptions

### Are all rounded corners bad?

No.

Rounded corners are not inherently bad.
But rounded corners applied without thought should be treated as suspects.

Border radius can have a role.
It can soften a surface.
It can create hierarchy.
It can suggest interactivity.
It can guide visual flow.

But in AI-generated UI, border radius often stops being a role and becomes a reflex.

And a reflex is not design.

### Are all card layouts bad?

No.

Cards are useful.
They can group related information well.

But when everything becomes a card, everything starts to look equally important.

Eventually, the page exists only to display cards.

Users did not come to see cards.
They came for information.

### Is it bad to use AI for UI?

No.

AI is useful.
AI is fast.
AI is good for first drafts.

But if you trust the first draft too much, everything becomes round.

AI is good at averages.
And the average modern web UI is a little too round.

## Finally

This skill exists to make AI-generated UI feel slightly more human.

It reduces rounded corners, removes suspicious badges, questions vague copy, and thins out the SaaS-template smell.

But there is unfortunate news.

Even after all of that, the best solution is still:

**Have a human think carefully and design it properly in the first place.**

We ask AI to create the UI.
Then we ask AI again to remove the AI-ness from the UI.

Very advanced.

Almost prehistoric.

## License

MIT

No rectangles were harmed in the making of this project.
Several pill badges, however, were quietly dealt with.
