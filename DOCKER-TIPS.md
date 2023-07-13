# DOCKER TIPS

### Fix `qemu: uncaught target signal 6 (Aborted) - core dumped` on Mac M1 when run `flutter compose up -d`

- Add to font-end:

```
platform: linux/amd64
```

