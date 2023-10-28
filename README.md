# compose-for-quants

## Compose Key for Quants: Introduction

This project is an effort to document and create Compose key sequences which are useful for quants and 
mathematicians when typing their texts. The specifics of their work is that much of the text would normally be in a 
language like English, but often there would be a need to insert a Greek letter or a special mathematical symbol of 
some sort. This lets one avoid excessive clicking or confusing switching through many keyboard layouts, which would 
otherwise be required to get to the required symbol.

It is expected that the Compose sequences would not be useful in [TeX](https://en.wikipedia.org/wiki/TeX) documents 
as they solve the problem by introducing special backslash-sequences, but I may be wrong here.  

## What is "Compose Key"?

[Compose key](https://en.wikipedia.org/wiki/Compose_key) is a feature present on some systems which allows one to 
type symbols not present in the current keyboard layout.

It has existed at least since 1983 and has been appreciated by power-users since.
Not every system has it, however. Also, often it is disabled and pretty much every modern keyboard misses a 
dedicated button for it. Nevertheless, it can be enabled and there are keys which can be re-assigned to acts as a 
Compose key.

One of its uses is typing in a language without installing, learning, and switching to a different keyboard layout.
For example, your keyboard layout may be English, but you wish to type some text in German.
Sadly, German layout would be confusing as letters "Z" and "Y" are swapped, which is quite confusing.
But with English layout you cannot type letters "ß" and "ü". Compose key can help here.
If you need "ß", you just hit "Compose" "s" "s" and get "ß". Similarly, for "ü" you would hit "Compose" "s" "s".
Note, that the combinations are fairly easy to remember do not require acrobatics: you hit the keys individually 
rather than holding several keys at the same time as if playing [Twister](https://en.wikipedia.org/wiki/Twister_
(game)).

This is also quite useful when someone is typing a text in one language, but now and then needs to type a 
few individual characters from another one, or a symbol which does not actually belong to any natural language, like 
some mathematical symbols.  

## Installing the Sequences

At the moment, only Linux/UNIX systems and only English keyboard layouts are supported.

The installation sequence goes like this:

1. Please download [.XComspose](en/.XCompose) file and put it into your home directory.
2. Enable Compose key using whatever method is appropriate in your desktop environment (_I suggest using "Caps Lock" 
   for this purpose as its main use is SHOUTING ONLINE, which is not comme il faut anyway_).
3. Confirm that Compose Key works for you by hitting `Compose key` `-` `>`, which should yield `→`.
4. Then log out and log back in.
5. If you hit `Compose key` `g` `g` you should end up with `γ`.

## Using the Sequences

This version adds Greek letters, which allows you to type formulae easier.
It also allows you to use Greek letters in code. Some say it is ridiculous, but I do believe that quant code with
actual Greek letters is [more readable](https://rtveliashvili.name/post/2023-06-21/greek-letters-in-quant-code).

### Typing Greek Letters

The Greek sequences were largely based on the Greek keyboard layout.
The consequence is that some letters like "ν" and "ξ" can be typed in more than one way.

Almost all sequences have this form: `Compose key` `g` `<selector key>`, where "g" stands for "Greek".
For upper case Greek letters you need to press uppercase selector keys.

The mappings are below:

| Greek<br/>Symbol | Selector<br/>Key |
|-----------------|------------------|
| Α / α           | A / a            |
| Β / β           | B / b            |
| Γ / γ           | G / g            |
| Δ / δ           | D / d            |
| Ε / ε           | E / e            |
| Ζ / ζ           | Z / z            |
| Η / η           | H / h            |
| Θ / θ           | Q / q            |
| Ι / ι           | I / i            |
| Κ / κ           | K / k            |
| Λ / λ           | L / l            |
| Μ / μ           | M / m            |
| Ν / ν           | N / n or V / v   |
| Ξ / ξ           | C / c or J / j   |
| Ο / ο           | O / o            |
| Π / π           | P / p            |
| Ρ / ρ           | R / r            |
| Σ / σ           | S / s            |
| Τ / τ           | T / t            |
| Υ / υ           | U / u            |
| Φ / φ           | F / f            |
| Χ / χ           | X / x            |
| Ψ / ψ           | Y / y            |
| Ω / ω           | W / w            |

Also, if you wish to type "ς", which is a special variant of "σ", there is a special (but hopefully easy to 
remember) sequence for that.

So while for "σ" you would type `Compose key` `g` `s`, for "ς" you need to type `Compose key` `g` `,` `s`.

## Troubleshooting

By default, when Compose key is enabled, `Compose key` `-` `>` should produce `→`.
If that does not work -- try to fix that first.

If Compose key is enabled and some combinations work, but not the ones provided by this configuration, then
perhaps your system is not able to pick up user-defined configurations.

First, double-check that you do in fact have the configuration. In a terminal, run this:
```bash
cat ~/.XCompose
```

You should see the text of the configuration, not an error message.

Second, there used to be a problem that user-defined sequences were ignored if your input method is ibus.
In a terminal, try this:
```bash
set | grep _IM_
```

You can see something like this:
```
QT_IM_MODULE=ibus
```

This tells you which Input Method is in use. On old systems a switch to "xim" may help.
Look [here](https://askubuntu.com/questions/129680/how-can-i-make-ibus-not-ignore-xcompose) for more details. 