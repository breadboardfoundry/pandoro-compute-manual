# Using tmux for Long-Running Processes

When running ML training jobs or other long processes, network disconnects can interrupt your work. **tmux** solves this by keeping your terminal session alive on the server, even when you disconnect.

## Why Use tmux?

Without tmux:
- Closing your browser tab kills running processes
- Network interruptions terminate your training job
- You can't check on a job from a different device

With tmux:
- Processes continue running after you disconnect
- Reconnect anytime to see output and progress
- Run multiple terminal sessions in one window

## Quick Start

### Start a New Session

```bash
tmux new -s training
```

This creates a session named "training". Name your sessions descriptively.

### Detach from a Session

Press `Ctrl+b`, then `d`

Your processes keep running. You can close the browser safely.

### List Active Sessions

```bash
tmux ls
```

### Reattach to a Session

```bash
tmux attach -t training
```

Or use the shorthand:

```bash
tmux a -t training
```

## Common Workflow

1. **Start your work session**
   ```bash
   tmux new -s my-experiment
   ```

2. **Run your training script**
   ```bash
   python train.py --epochs 100
   ```

3. **Detach when needed**

   Press `Ctrl+b`, then `d`

4. **Come back later and reattach**
   ```bash
   tmux attach -t my-experiment
   ```

## Essential Commands Reference

| Action | Command |
|--------|---------|
| New named session | `tmux new -s name` |
| Detach | `Ctrl+b` then `d` |
| List sessions | `tmux ls` |
| Attach to session | `tmux attach -t name` |
| Kill session | `tmux kill-session -t name` |

## Multiple Windows in One Session

tmux can have multiple windows (like browser tabs) within one session.

| Action | Keys |
|--------|------|
| New window | `Ctrl+b` then `c` |
| Next window | `Ctrl+b` then `n` |
| Previous window | `Ctrl+b` then `p` |
| Select window by number | `Ctrl+b` then `0-9` |
| Rename window | `Ctrl+b` then `,` |

## Split Panes

View multiple terminals side by side:

| Action | Keys |
|--------|------|
| Split horizontally | `Ctrl+b` then `"` |
| Split vertically | `Ctrl+b` then `%` |
| Move between panes | `Ctrl+b` then arrow keys |
| Close current pane | `exit` or `Ctrl+d` |

## Tips for ML Researchers

### Monitor Training in One Pane, GPU in Another

1. Start tmux: `tmux new -s experiment`
2. Split vertically: `Ctrl+b` then `%`
3. In left pane: run your training script
4. In right pane: run `watch nvidia-smi` to monitor GPU
5. Switch panes with `Ctrl+b` then arrow keys

### Check on Jobs from Anywhere

Since your session lives on the server, you can:
- Start training from your office
- Check progress from home using the browser SSH
- Review results from your phone (the web interface works on mobile)

## Troubleshooting

**"sessions should be nested with care"**

You're already inside tmux. Don't start tmux inside tmux. Check with:
```bash
echo $TMUX
```
If it prints a path, you're already in tmux.

**Session disappeared after server restart**

tmux sessions don't survive server reboots. For critical long-running jobs, consider using a process manager or saving checkpoints frequently.
