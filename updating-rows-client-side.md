The service request object can update rows from the client.

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



