
# Linux Überlebenshandbuch 

Dieses Buch könnte Ihr Leben retten!

Praktisches Survival-Buch zum Überleben in Linux. So wunderschön Linux auch ist, so hilflos sind wir ihm im schlimmsten Fall ausgeliefert!

## Noch eine Linux Buch?

Eine Sammelsurium von Befehlen die man ständig vergisst. 

## Table Of Contents

### Prologue

- [Kapitel 0 - Einleitung](./kapitel00_einleitung.md)

### Erster Teil: 

- [Kapitel 1 - Bash](./teil01_kapitel01_bash.md)
- [Kapitel 2 - Systemd](./teil01_kapitel02_systemd.md)
- [Kapitel 3 - cronjobs](./teil01_kapitel03_cronjobs.md)


erst Disk vergrößern,
dann Partition vergrößern

```
parted /dev/sdd resizepart 1 '100%'
parted /dev/sdd print
resize2fs /dev/sdd1
```
Belegten Festplattenplatz ermitteln

```
du -h --max-depth 1 ./ | sort -h
```

- [Ch 2     - tmux](./ch02_tmux.md)

### Zweiter Teil: 

- [Ch 22 - Vim](./ch22_.md)
- [Ch 23 - docker](./ch23_docker.md)


### Dritter Teil: 

- [Ch 25 - Vimscript Basic Data Types](./ch25_vimscript_basic_data_types.md)
- [Ch 26 - Vimscript Conditionals And Loops](./ch26_vimscript_conditionals_and_loops.md)
