##Overview
 Renode does not natively support GR740 emulation.
 This repository provides a GR740 platform description (`.repl`) for creating a GR740 emulation machine.

---

##Usage
1. Start Renode
2. Run the following commands in the Renode monitor
```shell
  mach create your-machine-name
  using sysbus
  machine LoadPlatformDescription @yourpath/platforms/cpus/gr740.repl
  sysbus LoadELF @your-application
```
3. Apply additional required settings (if any)
4. Start
```shell
  start
```
