## Why I picked recall over precision here

For this churn problem I think missing a churner is worse than false alarming a loyal customer.

If I miss a churner (false negative) that means the model told us this person is fine but they actually leave. The company loses that customer completely. All their future payments are gone and now the company has to spend money to find a new customer to replace them. This is a big loss and we cannot fix it once it happens.

If I false alarm a loyal customer (false positive) that means the model said this person might leave but they were never going to leave. The company just sends them a small discount or a check in call. This costs some money but it is small and it does not really hurt anything. The customer might even feel good that the company reached out.

So one mistake is big and permanent and the other mistake is small and can be fixed. Because of this I think recall matters more than precision for this problem. This is why I used class_weight balanced. It made the recall go up from 0.55 to 0.78 for the churn class. Yes precision went down and accuracy went down too but I think that is an ok trade for this business case.

One thing to keep in mind is that with 0.51 precision about half the people the model flags are not really going to churn. If the retention offer is expensive this trade might need to be looked at again.