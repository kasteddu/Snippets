***My preferred ALIAS***

.bash_aliases


```bash
#----------------------------------------------------------------------- Some more ls aliases - originale di bashrc
alias ll='ls -lahF'
alias la='ls -A'
alias l='ls -CF'
#----------------------------------------------------------------------- Vai al sito
alias sito='cd /var/www/html/'

#--- check log
alias log_errori='sudo tail /var/log/lighttpd/error.log'
alias log_fail2bal='sudo tail /var/log/fail2ban.log'
alias log_syslog='sudo tail /var/log/syslog'

#--- IP to exclude from site log
alias log_sito="cat /var/log/lighttpd/lighttpd.log | grep -v 'IP1\|IP2\'"

alias logga='cat /var/log/syslog'

#----------------------------------------------------------------------- reload bash rc
alias reloadbash='. ~/.bashrc'


#----------------------------------------------------------------------- docker
alias dkdj='cd /home/[USER]/dk/djdk/ && docker-compose up -d && cd'
alias dkdjoff='cd /home/[USER]/dk/djdk/ && docker-compose down && cd'
alias dkgh='cd /home/[USER]/dk/ghdk/ && docker-compose up -d && cd'
alias dkghoff='cd /home/[USER]/dk/ghdk/ && docker-compose down && cd'

```
