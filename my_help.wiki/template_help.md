# template_helpの出力結果

```
bob% bundle exec exe/template_help --to_hiki
ヘルプのサンプル雛形.
headに常に表示される内容を記述.
---
<<<
  ヘルプのサンプル雛形.
  headに常に表示される内容を記述.
単元
  c-f, move Forwrard,    前or右へ
  フォーマットは自由です.
単元2
  c-f, move Forwrard,    前or右へ
  フォーマットは自由です.
```

# template_helpの中身
helpの実態は~/.my_helpに保存されたYAML形式のfileです．書き方はコメントを参照ください．

```ruby
---
#start header, which appears every time.
:head:         #never change
- ヘルプのサンプル雛形               #describe the contents breafly.
- "  headに常に表示される内容を記述" #head '- ' is necessary
:license:         #never change
- "     cc by Shigeto R. Nishitani, 2016"  #show licence
# start the first item
:item:         #change snake word
  :opts:          #never change
    :short: -i      #change short option
    :long: --item   #change long option
    :desc: 単元(item) #describe what for in help list
  :title: 単元  #describe what for in each help
  :cont:              #the following lines are appeared.
  - c-f, move Forwrard,    前or右へ  #top '  - ' are necessary for yaml format
  - フォーマットは自由です. 

# start the second item... and so on.
:item2: 
  :opts: 
    :short: -j
    :long: --item2
    :desc: 単元2(item2)
  :title: 単元2
  :cont:
  - c-f, move Forwrard,    前or右へ
  - フォーマットは自由です. 
```
