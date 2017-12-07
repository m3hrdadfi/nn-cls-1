# Add new jupyter kernel

### Step 1

```
$ conda create -n py35 python=3.5 ipykernel
```

### Step 2

```
$ source activate py35
```

### Step 3

```
$ ipython kernel install --user --name py35 --display-name "Python (py35)"
```

### step 4

```
$ source deactivate
```

### step 5

```
$ jupyter kernelspec list
```

