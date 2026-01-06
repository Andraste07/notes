```table-of-contents
```

## Terraform repository setup (first time)

```
git init
git branch -m main
git add .
git status

git commit -m "initial terraform structure with ipam and proxmox"

git remote add origin http://forgejo.void.internal:3000/FidannaLabs/terraform.git

git push -u origin main
```

## Commit & Push

```
git status
git diff
git add terraform.tfvars
git commit -m "x"
git pull --rebase
git push

git add . && git commit -m "recover old files" && git push

```

## Pull request workflow

```
git status #check in which branch i am
git checkout main # if i am not in main
git pull

git checkout -b feature-x
# arbeiten

git add .
git commit -m "feat: x"
git push -u origin feature-x

# PR im UI[/home/fidan/Study/iac/.forgejo/workflows/deploy.yml](file:///home/fidan/Study/iac/.forgejo/workflows/deploy.yml)
# CI grün
# Merge im UI

git checkout main
git pull
git branch -d feature-x

git branch -l #list branches

```

## Pull request workflow (forgot to create a branch)

```
git status 
git checkout -b feature/ipam-host-resolution
git add .
git commit -m "Add host definition parsing and IPAM resolution"
git push -u origin feature/ipam-host-resolution

```

## Proxmox cleanup & Terraform state reset

```
pct stop 777
pct destroy 777

qm stop 788
qm destroy 788

rm -f terraform.tfstate terraform.tfstate.backup
rm -rf .terraform/
```

## Proxmox host reset + shutdown

```
pct shutdown 100
pct shutdown 102
pct shutdown
qm shutdown 101
pct list
qm list

shutdown -h now
```

## Commit Msg

```
init – erstmaliges Setup
feat – neue Funktion    
chore – Aufräumen, Struktur, Meta    
test – Tests oder Testumgebungen    
docs – Doku
```