# Accessing k3s remotely

1. From your VPS, copy over `/etc/rancher/k3s/k3s.yaml` into `~/.kube/config` on your local machine.

2. Figure out a way to connect to you server. I used Tailscale. Once you have the node address, replace the `server` value in `~/.kube/config` with your node address.

3. On your remote node, create a new file at `/etc/rancher/k3s/config.yaml` and add the following:
```yaml
tls-san:
  - <YOUR_NODE_ADDRESS>
```
This is equivalent to adding the `-tls-san=<YOUR_NODE_ADDRESS>` to the server arguments.

4. Finally, restart k3s
```bash
$ systemctl restart k3s
```

Now your local `kubectl` should be able to access the remote node 🎉