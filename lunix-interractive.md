Check node’s availability *[sinfo]*
>sinfo

allocate node *[ salloc, - partition name, - time]*
> salloc -p defq -t 2-00:00:00

Check jobs & nodes in queue *[squeue, -user name]*
>squeue -u adbe

Connect to a node *[ssh, node name]*
> ssh node134 

Run batch script: *[sbatch, script_name]*
>sbatch my_script.sh

Check Progress: *[list_files, currently running]*
>ls -ltrh

Check user's node status *[account, user name]*
> acct -u adbe 

Check memory in use *[account , user name, top]*
> acct -u adbe top

Close connection to a node *[exit]*
> exit

Cancel a job *[scancel, job number]*

> scancel 601356 
> 
Create bash script *nano, file_name]*
> nano my_script.sh
