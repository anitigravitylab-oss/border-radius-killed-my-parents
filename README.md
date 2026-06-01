# border-radius-killed-my-parents

> AIは、今日も何の罪もない四角形に `border-radius: 9999px` を与えている。  
> もう、誰かが止めなければならない。

`border-radius-killed-my-parents` は、AIが生成したフロントエンドにありがちな「とりあえず丸くしておけば今っぽいでしょ？」という思想を矯正するためのデザインスキルです。

名前はふざけています。  
思想はわりと本気です。

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

## なぜ作ったのか

AIにフロントエンドを作らせると、最初はいい感じに見えます。

でも、よく見ると全部が丸い。

ボタンも丸い。  
カードも丸い。  
バッジも丸い。  
入力欄も丸い。  
アイコンの背景も丸い。  
意味のない装飾も丸い。  
存在理由の分からないCTAも丸い。

どうしてそんなに丸くしたがるのか。

前世で角に足の小指でもぶつけたのでしょうか。

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

良いUIは、  
「私は40,000個のSaaSランディングページを学習したAIが、深夜2時に生成しました」  
という顔をしていない方がいい。

## 何を直すのか

このスキルは、プロジェクト内のAIっぽいデザインパターンを見つけます。

ただし、すべての角丸を絶滅させるわけではありません。

必要な角丸は残します。  
不要な角丸は減らします。  
意味のない装飾は削ります。  
何も説明していない抽象語は疑います。  
謎のバッジ群は取り調べます。  
SaaSっぽいだけの空気を抜きます。

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

## 使いどころ

AIに作らせたフロントエンドを見て、こう思ったときに使ってください。

> なんで全部こんなに丸いんだ？

または：

> なんで意味のないバッジが17個も並んでるんだ？

または：

> これはポートフォリオなのか、存在しないB2B SaaSのLPなのか？

または：

> このUI、何も悪いことはしていないのに、なぜか腹が立つ。

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

重症化すると、以下のような症状が出ます。

> すべての要素が白いカードの中に入り、
> すべてのカードが角丸になり、
> すべての角丸が影を持ち、
> すべての文章が「あなたの〇〇を次のレベルへ」で終わる。

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

## 最後に

このスキルは、AI生成UIを少しだけ人間らしくするためのものです。

角丸を減らし、謎バッジを消し、抽象語を疑い、SaaSテンプレート臭を薄める。

しかし、残念なお知らせがあります。

ここまでやっても、結局いちばん良いのは、
**最初から人間がちゃんと考えて作ることです。**

AIに作らせて、AIっぽさを消すためにまたAIを使う。

私たちは今、かなり遠回りな方法で、
「人間がデザインする」という地点に戻ろうとしています。

## License

MIT

このプロジェクトの制作中、四角形は傷つけられていません。
ただし、いくつかのピル型バッジは静かに処理されました。

---

# English

# border-radius-killed-my-parents

> AI keeps giving innocent rectangles `border-radius: 9999px`.
> Someone had to stop it.

`border-radius-killed-my-parents` is a design skill for correcting one of the most suspicious habits of AI-generated frontend code:

> "Just round everything and call it modern."

The name is a joke.
The grudge is only half a joke.

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

## Why?

When AI generates a frontend, it often looks good for the first three seconds.

Then you look closer.

Everything is round.

The buttons are round.
The cards are round.
The badges are round.
The inputs are round.
The icon backgrounds are round.
The meaningless decorations are round.
Even the CTA with no clear reason to exist is round.

Why does AI want everything to be so round?

Did a sharp corner hurt it in a past life?

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

Good UI should not look like:

> "I was generated at 2 a.m. by an AI trained on 40,000 SaaS landing pages."

## What does it fix?

This skill looks for AI-ish design patterns inside a project.

It does not blindly destroy every rounded corner.

It keeps useful rounded corners.
It reduces unnecessary rounded corners.
It removes meaningless decoration.
It questions vague abstract copy.
It interrogates suspicious badge clusters.
It lets the fake SaaS air out of the room.

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

## When to use it

Use this when you look at an AI-generated frontend and think:

> Why is everything so round?

Or:

> Why are there 17 meaningless badges?

Or:

> Is this a portfolio, or a landing page for a B2B SaaS product that does not exist?

Or:

> This UI has done nothing wrong, yet somehow it offends me.

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

In severe cases:

> Every element enters a white card,
> every card gets rounded corners,
> every rounded corner gets a shadow,
> and every sentence ends with "take your ___ to the next level."

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
