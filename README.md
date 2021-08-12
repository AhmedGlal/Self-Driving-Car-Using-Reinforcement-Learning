# Self-Driving-Car-Using-Reinforcement-Learning
Most of the current self-driving cars make use of multiple algorithms to drive. Furthermore, most of the approaches use supervised learning to train a model to drive the car autonomously. This approach leads to human bias being incorporated into the model. We implement the Deep Q-Learning algorithm to control a simulated car, end-to-end, autonomously. 

# All Problem Solving

##FIRST>>

orch.multinomial(input, num_samples, replacement=False, out=None)

Returns a tensor where each row contains num_samples indices sampled from the multinomial probability distribution located in the corresponding row of tensor input.

Change the code as below:

def select_action(self, state):
    probs = F.softmax(self.model(Variable(state, volatile = True))*7)
    action = probs.multinomial(1) # 1 is the number of samples to draw
    return action.data[0,0]

.....................................................................................................
##SECOND>>>

td_loss.backward(retain_graph = True)
It worked.


........................................................................................................
##THIRD>>>

I had the same problem. I solved it by first Kivy and its dependencies:

* python -m pip uninstall kivy

* python -m pip uninstall kivy.deps.sdl2

* python -m pip uninstall kivy.deps.glew

* python -m pip uninstall kivy.deps.gstreamer

* python -m pip uninstall image

* Now reinstalling everything except gstreamer.

<THEN>

* python -m pip install --upgrade pip wheel setuptools

* python -m pip install docutils pygments pypiwin32 kivy.deps.sdl2 kivy.deps.glew --extra-index-url https://kivy.org/downloads/packages/simple/

* python -m pip install kivy
