# Data Services

#### Service Calls

The service request object can update rows from client side code \(typically ts files\).

```typescript
Q.serviceCall({
    service: 'EndpointBaseURL/Update', 
    request: {
        EntityId: 2,
        Entity: {
            Name: 'Thisisaname',
            ParentId: 1
        }
    }
});
```



