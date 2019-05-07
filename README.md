# THOP: PyTorch-OpCounter

## How to install 
* Through PyPi
    
    `sudo pip3 install thop`
    
* Using GitHub (always latest)
    
    `sudo pip3 install --upgrade git+https://github.com/githubgzc/pytorch-OpCounter`
    
## How to use 
* Basic usage 
    ```python
    from torchvision.models import resnet50
    from thop import profile
    model = resnet50()
    flops, params = profile(model, input_size=(1, 3, 224,224))
    ```    

* Define the rule for 3rd party module.
    
    ```python
    class YourModule(nn.Module):
        # your definition
    def count_your_model(model, x, y):
        # your rule here
    flops, params = profile(model, input_size=(1, 3, 224,224), 
                            custom_ops={YourModule: count_your_model})
    ```
    
