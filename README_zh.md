# satori

satori 是一个随机生成符卡战的小工具。

## 使用

Clone 这个仓库并运行 `main.py`.

```bash
# Install dependencies
pip3 install tomlkit
# Clone and run
git clone https://github.com/Ravenclaw-OIer/satori
python3 satori/main.py reimu marisa # change reimu and marisa to whoever you want
```


## 规则
satori 从~~你心中~~ `characters.toml` 中读取符卡信息。


### Rounds

A spellcard fight is consisted of several rounds, it will continue until one of the players has her hp strictly lower than 0.

In each round, the following events happen in chronological order:

1. A random number is generated between 0 and the `atk` value of both players. This value is the `atk` value used for comparison in this round.
2. The one with the higher `atk` value for this round will be the attacker. A spellcard is randomly picked from her spellcards.
3. A number is randomly picked between the two values specified in the spellcard's `harm` field. This is the harm (hp drop) caused by this spellcard. This value may be 0.
4. The harm is applied.
5. If the spellcard comes with shields, hp boosts or atk boosts, it is applied.
6. The round ends, if both player have their hp >= 0, return to step 1.

### Spellcards

Each spellcard has the following fields:

+ `name`: a string, the name used to refer to the spellcard *within the program*
+ `display_name`: a string, the displayed name of the spellcard.


## Contributing

You can contribute by

- Writing more spellcards
- Implementing complex spellcard behaviors
- Simply playing around and report bugs

## License

This program is free software, you can redistribute it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3, or, at your option, any later version.

