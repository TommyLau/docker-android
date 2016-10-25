# Docker AOSP

## How to use

```
docker run --name=aosp -t -i -v /path/to/src:/aosp tommylau/aosp bash
```

## New method

The new method enables SSH Server, so it can let multiple users to access the AOSP on a server.

```
docker run --name="aosp" -v /path/to/home:/home -p 22 -d tommylau/aosp
```

Enter the root shell by running:

```
docker exec -ti -u root aosp bash
```

And add user account like normally in *nix environment:

```
adduser username
```
