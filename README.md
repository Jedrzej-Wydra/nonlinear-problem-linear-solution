# Approximating the Curves with Straight Lines (Yes, Really)
author: Jędrzej Wydra

## Short summary
Implemented a sliding-window approach with local linear models in Python to approximate nonlinear functions, using gradient descent for sequential parameter updates.

## Technical summary
Generated noisy sine-wave data and applied linear regression fitted via gradient descent on small, overlapping windows to locally approximate the function. Combined local predictions to reconstruct the global nonlinear shape, demonstrating Taylor-based local linearity. Visualized approximation quality and compared single global vs. multi-window linear fits using Python.

## History
Complex tools for complex problems? Not always necessary. In this project, I set out to answer a simple question: can a nonlinear function be reconstructed using a simple linear model? The answer, delightfully, is yes — under the right conditions.

To demonstrate, I generated noisy data from a sine function, then fitted a single linear model across the full range. The result? Unsurprisingly poor. But then I tried something different: online learning in a sliding window. For each window, I trained a local linear model and saved the prediction — shifting the window step by step.

The effect was surprisingly good. Despite using only linear models, the global shape of the sine function was captured quite well. The output depends on whether you log predictions from the beginning, middle, or end of each window — but in every case, the trick worked. Why? Because of the Taylor theorem: any smooth function can be locally approximated by a linear one. In this case, “locally” meant “within a window.”

So no magic, no neural networks — just a clever way to let simple math do the heavy lifting.

## Side note
Sometimes, you don’t need a nuclear warhead to swat a fly. And in the age of machine learning hype, that’s worth repeating. Neural networks are powerful, sure — but also expensive, complex, and often overkill. A well-placed linear model can get the job done just fine. As we say in Poland: "Don’t use a cannon to shoot a fly." In this case, I’d say: don’t nuke the fly — try a straight line first.
