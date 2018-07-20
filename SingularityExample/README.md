# Singularity Example

## A singularity container to run [Diamond](https://github.com/bbuchfink/diamond), a sequence aligner for protein and translated DNA searches. This was built as part of an exercise during the NSF Cyber Carpentry on 'Data Life-Cycle' training.

### Instructions to use this repo to build the singularity image and run the container.

1. Download this repo

```
git clone https://github.com/Gkandoi/SingularityExample.git
```

2. Go into the repository

```
cd SingularityExample
```

3. Build the singularity image using the 'Singularity' file included in this repository.

```
sudo singularity build diamond.simg Singularity
```

4. Run the singularity image

```
singularity run diamond.simg
```

This should result in a message similar to this:

```
Error: Syntax: diamond COMMAND [OPTIONS]. To print help message: diamond help
```

This error message shows that the image is running with diamond in it. The message is actually from diamond which says that we need to give diamond some commands to execute. So, let's try to run some sample diamond commands.

5. Build a sample database using diamond

```
singularity run diamond.simg diamond makedb --in /zebrafish.1.protein.faa -d zebrafish_db
```

This will create a database file zebrafish_db using the sample zebrafish protein sequence fasta file.
