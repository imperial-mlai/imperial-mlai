# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:**
Model inputs are the parameters to the Black-Scholes vanilla call option pricing model:

S		- asset price
K		- option strike price
r		- risk free interest rate
sigma	- asset volatility
t		- time to maturity

**Output:** 
The output of the model is the price of the option, expressed as a percentage of current spot

**Model Architecture:** 
The model uses a neural net with four layers - an input layer, two hidden layers and an output layer.

## Performance

The model was able to replicate the Black-Scholes option price fairly well with limited tuning.  We measured performance by simply comparing the model output with the analytic Black-Scholes solution.

## Limitations

The model accuracy could be improved with a deeper architecture and better hyper-parameter tuning.  The span of the input space could also be extended - the model was trained on a space that is probably good enough for most typical applications but extreme cases of rates and volatities need to be investigated and checked.

## Trade-offs

To train this model we used a lot of training data.  This was easy to do as we were generating the training data from the analytical Black-Scholes pricing model.  For more complicated derivatives though (especially those that use Monte Carlo for accurate pricing) this could be problematic.

