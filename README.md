# Bitburner scripts collection

Collection of [Bitburner](https://danielyxie.github.io/bitburner/) scripts. 

- Auto Hacking + acquiring targets
- Better Scan (manual, run scan.ns)
- Auto hacknet purchase  (manual, run hacknet.ns)

## Instalation

1. Create a new script called `start.ns` with the following content:

```javascript
export async function main(ns) {
  if (ns.getHostname() !== "home") {
    throw new Exception("Run the script from home");
  }

  await ns.wget(
    `https://raw.githubusercontent.com/notidentical/bitburner/master/src/initHacking.ns?ts=${new Date().getTime()}`,
    "initHacking.ns"
  );
  ns.spawn("initHacking.ns", 1);
}
```

2. Exit the nano and write in console: `run start.ns`
