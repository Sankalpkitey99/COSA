# Linux CMD's

##  Basic Permission Commands
- `ls -l` – View file/directory permissions.
- `chmod u+x filename` – Add execute to user.
- `chmod g-w filename` – Remove write from group.
- `chmod o+r filename` – Add read for others.
- `chmod 755 filename` – Set permissions to `rwxr-xr-x`.
- `chmod 644 filename` – Set permissions to `rw-r--r--`.

---

##  Ownership Commands
- `sudo chown sankalp filename` – Change file owner to `sankalp`.
- `sudo chown :groupname filename` – Change group ownership.
- `sudo chown sankalp:groupname filename` – Change both owner and group.
- `chown -R user:group /path/` – Recursively change ownership.

---

## Recursive Permission Change
- `chmod -R 755 /dir` – Recursively set permissions.
- `chown -R sankalp:group /dir` – Recursively change owner:group.

---

## Special Permissions (Advanced)
- `chmod 4755 file` – Set **SetUID** (runs with owner's privilege).
- `chmod 2755 file_or_dir` – Set **SetGID** (shared group exec or directory files).
- `chmod 1777 /dir` – Set **Sticky Bit** (only owner can delete).
- `ls -l` – Shows `s` or `t` for special bits.
- `stat filename` – Detailed permission + ownership info.

---

## Practice Command Snippets
- `touch testfile` – Create a new file.
- `chmod 740 testfile` – Set permissions to `rwxr-----`.
- `mkdir shared` – Create directory.
- `chmod 1777 shared` – Full access, only owner can delete inside.
- `ls -ld shared` – View permissions of a directory.
- `chmod 4755 script.sh` – Set **SetUID** on script.
- `chmod 2755 script.sh` – Set **SetGID** on script.
