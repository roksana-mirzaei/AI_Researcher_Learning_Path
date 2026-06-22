# pytorch docs:
https://docs.pytorch.org/docs/2.12/generated/torch.nn.Module.html



If you are new to implementing the models from scratch using pytorch, this guide will help you to better understand the nn.Module components.

# What is torch.nn?
torch.nn is PyTorch building and training neural networks. it intricate details of neural network operations. Like instead of manually coding matrix operarions for forward and backward passes, it has buil-in layers and  functions


when you implement nn.Module, in fact you are inherting PyTorch neural network systems. every model in PyTroch is essentially subclass of nn.Module. It provides the following:
**initializarion (__init__):** define the layers and component of your network
**Forward Pass (forward):** it sepecifies how data flows through the layers of network
**Parameter Management:** automatically track and oprimize model parameters. for example 

`
self.embed = nn.Embedding()
`
This register parameters automtically. PyTorch will scans the attributes of the class, finds nn.Parameter tensor and stores them in .parametres()

so later on:

`
optimzer = torch.optim.Adam(model.paramters)
`    
it works perfetly

It also allowas gradient tracking hook, pramaters inside nn.Module have

`
requires_grad = True
`

So during backprop:

`
loss → backward() → gradients computed → stored in .grad
`


It also has `.to(device) ` support. So when `model.cuda()` . It moves ALL parameters inside modules automatically.



# further learning:
How pytorch autograd works:
https://docs.pytorch.org/tutorials/beginner/blitz/autograd_tutorial.html


How Computational Graphs are Constructed in PyTorch:
https://pytorch.org/blog/computational-graphs-constructed-in-pytorch/

PyTorch execution model:
https://docs.pytorch.org/executorch/stable/intro-section.html


PyTorch internal architecture for beginners:
https://pytorch.org/blog/a-tour-of-pytorch-internals-1/



