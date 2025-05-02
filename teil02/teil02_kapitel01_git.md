# Git

## Github and Personal Token Bullshieetha

 ```
 vim README.md
 git add README.md
 git commit
 git commit --amend --reset-author
 git push origin main
```


## Git Einstellungen

```
git config --global core.editor "vim"
```

## Git Commit-Nachrichten vor dem push ändern

to alter, modify, rephrase, or add to or subtract from (a motion, bill, constitution, etc.) by formal procedure

```
git commit --amend
```

## github und die Sicherheit 

Damit man im Jahre 2023 mit Github noch arbeiten kann wurden spezielle Token ersonnen die die 
Sicherheit verbessern und die Nutzererfahrung verschlechtern. Im Git hub muss ein Token 
erzeugt werden der für alle Repros gültig sein kann. 


Token: all_access:


GitHub account, go to Settings 
→ Developer Settings 
→ Personal Access Token 
→ Tokens (classic) 
→ Generate New Token (Give your password) 
→ Fillup the form → click Generate token 
→ Copy the generated Token, it will be something like ghp_sFhFsSHhTzMDreGRLjmks4Tzuzgthdvfsrta



## neu erzeugte Dateien Repository hinzufügen

git mitteilen das es neue Dateien gibt:
```
git add datei1 datei2
```

git mitteilen das es Änderungen gibt die übernommen werden sollen
```
git commit
```

Die daten ins Git Repository schieben
```
git push
```

## Git push vs. pull

+ Daten in das Repositorie schieben push
+ Daten aus dem Repository ziehen pull



