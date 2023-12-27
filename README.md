# frog.mikr.us

Repozytorium zawiera workflow dla github actions, który raz w tygodniu wchodzi na serwer z frog.mikr.us i odpala kilka komend by utrzymać serwer przy życiu i nie pozwolić na jego usunięcie. 

Dzięki Kuba za  świetny projekt. 👏 👍

## jak to działa?

Zrób sobie forka tego repozytorium i włącz github actions.

W zakładce Settings -> Secrets and variables -> Actions dodaj następujące wpisy:

* `SSH_HOST` - adres serwera np. frog01.mikr.us
* `SSH_USER` - nazwa użytkownika na serwerze
* `SSH_KEY` - klucz prywatny ssh do serwera
* `SSH_PORT` - port ssh na serwerze zgodny z dokumentajcą FROGa

Oczywiście musisz wygenerować sobie klucz ssh np.: 

```bash
ssh-keygen -t ed25519 -C "frog@twoja-domena-pl" -f ./frog-github-actions
```

A następnie dodać go do serwera:

```bash
ssh-copy-id -i ./frog-github-actions.pub -p ${SSH_PORT} ${SSH_USER}@${SSH_HOST}
```

## Dokumentacja frog.mikr.us

https://mrugalski.notion.site/Mikrus-Frog-955220f6de8145a69b837cf12e96ae1f

<!-- v1 -->
