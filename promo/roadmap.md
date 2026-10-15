# Roadmap: the path to the openalias Target

This is the path, not the code. Each milestone says what you learn, what you build, and how you know it works. Pick one and open a pull request. See [CONTRIBUTING.md](../CONTRIBUTING.md).

## Session 4: Noise-proof recovery

**You will learn:** How measurement error spoils a ladder match and how to choose a match tolerance, or score candidates, instead of demanding equality.

**You will build:** A recovery function that takes noisy apparent speeds and returns the most likely true speed with an uncertainty.

**Checkpoint (not met by the shipped code):** With Gaussian measurement noise of 0.3 rev/s on both apparent speeds (30 and 24 fps, true speed uniform from 5 to 59 rev/s), the recovered speed is within 0.5 rev/s in at least 95 percent of 2000 trials (the shipped `recover_frequency` manages about 52 percent).

**Difficulty:** intermediate

## Session 5: A third clip

**You will learn:** Why adding a third frame rate extends the unambiguous range, and how to choose the three rates.

**You will build:** A recovery function for three clips with a unique answer over a wide range.

**Checkpoint (not met by the shipped code):** With rates 30, 24 and 25 fps, the true speed 22.5 rev/s is the only candidate below 400 rev/s (two clips leave 4 candidates: 22.5, 142.5, 262.5 and 382.5).

**Difficulty:** intermediate

## Session 6: Fans with many identical blades

**You will learn:** Why only the pattern frequency N f is visible, and what an apparent speed means for a wheel with N spokes.

**You will build:** A clip renderer and a measurement function for N identical blades, with one blade tinted to tell them apart.

**Checkpoint (not met by the shipped code):** Recover the speed of a 6-blade fan at 17.4 rev/s from clips at 30 and 24 fps to within 0.1 rev/s, with only one blade tinted (the shipped code has no multi-blade clips).

**Difficulty:** advanced

## Session 7: A fan that spins up

**You will learn:** Time-frequency analysis (a spectrogram) of a signal whose speed changes, and how to unfold a folded ridge.

**You will build:** A tracker that follows the folded apparent speed through time and reconstructs the true speed curve.

**Checkpoint (not met by the shipped code):** A fan that speeds up from 0 to 40 rev/s in 4 seconds, filmed at 30 fps, has its final speed recovered to within 0.5 rev/s (the shipped code assumes a constant speed).

**Difficulty:** advanced

## Session 8: Real cameras: variable frame rate and rolling shutter

**You will learn:** How uneven frame timestamps and row-by-row readout change the apparent speed.

**You will build:** A simulator with frame timestamps from a clock with 0.5 percent jitter and a line-by-line shutter, plus a correction.

**Checkpoint (not met by the shipped code):** The recovered speed of a 22.5 rev/s fan is within 0.2 rev/s when frame timestamps carry 0.5 percent random timing error.

**Difficulty:** advanced

## The final step

Combine the milestones: recover the true speed of a fan with several identical blades that spins up, from noisy clips filmed at three frame rates by a camera with imperfect timing, and report an uncertainty. If your result looks like the Target animation, open a pull request and tell us how you did it.
