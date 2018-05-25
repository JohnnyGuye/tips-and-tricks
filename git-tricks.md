# Colored tree
git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all^C

# Stats user
git log --shortstat --author="$1" | grep -E "fil(e|es) changed" | awk '{files+=$1; insert\|
ed+=$4; deleted+=$6; delta+=$4-$6; ratio=deleted/inserted} END {printf "Commit stats:\n- File\|
s changed (total)..  %s\n- Lines added (total)....  %s\n- Lines deleted (total)..  %s\n- Tota\|
l lines (delta)....  %s\n- Add./Del. ratio (1:n)..  1 : %s\n", files, inserted, deleted, delt\|
a, ratio }'
