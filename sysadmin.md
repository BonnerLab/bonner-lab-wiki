# Notes for system adminstrators

## Setting up a new system

### Shared `/data` directory

- Create a shared `/data` directory: `sudo mkdir /data`
- Set permissions as follows
  - Run the following commands
    - `sudo chown -R root:cog-mb-group /data`
    - `sudo chmod -R g+s /data`
    - `sudo setfacl -m g::rwx /data`
    - `sudo setfacl -d -m g::rwx /data`
  - Ensure that the output of `getfacl /data` is:
    ```
    # file: data
    # owner: root
    # group: cog-mb-group
    # flags: -s-
    user::rwx
    group::rwx
    other::r-x
    default:user::rwx
    default:group::rwx
    default:other::r-x
    ```

### Installing `miniconda`

Use the installer to install to `/data/shared/miniconda3`.

### Other software

- Install the Nvidia drivers (ask brain-it to do it)
- Install `git`
