## Summary
The `GiftCardService` class is responsible for managing gift cards. It provides methods for creating, updating, and deleting gift cards, as well as retrieving gift card information and usage history.

## Example Usage
```csharp
// Creating a new gift card
var giftCard = new GiftCard();
await giftCardService.InsertGiftCardAsync(giftCard);

// Updating a gift card
giftCard.Amount = 50;
await giftCardService.UpdateGiftCardAsync(giftCard);

// Deleting a gift card
await giftCardService.DeleteGiftCardAsync(giftCard);

// Retrieving gift card information
var giftCardId = 1;
var retrievedGiftCard = await giftCardService.GetGiftCardByIdAsync(giftCardId);

// Retrieving all gift cards
var giftCards = await giftCardService.GetAllGiftCardsAsync();

// Retrieving gift cards based on specific criteria
var purchasedWithOrderId = 1;
var usedWithOrderId = 2;
var createdFromUtc = DateTime.UtcNow.AddDays(-7);
var createdToUtc = DateTime.UtcNow;
var isGiftCardActivated = true;
var giftCardCouponCode = "GIFT123";
var recipientName = "John Doe";
var pageIndex = 0;
var pageSize = 10;
var filteredGiftCards = await giftCardService.GetAllGiftCardsAsync(purchasedWithOrderId, usedWithOrderId, createdFromUtc, createdToUtc, isGiftCardActivated, giftCardCouponCode, recipientName, pageIndex, pageSize);
```

## Code Analysis
### Main functionalities
- Creating, updating, and deleting gift cards
- Retrieving gift card information and usage history
- Filtering gift cards based on specific criteria
___
### Methods
- `DeleteGiftCardAsync`: Deletes a gift card.
- `GetGiftCardByIdAsync`: Retrieves a gift card by its identifier.
- `GetAllGiftCardsAsync`: Retrieves all gift cards or filters them based on specific criteria.
- `InsertGiftCardAsync`: Inserts a new gift card.
- `UpdateGiftCardAsync`: Updates an existing gift card.
- `GetGiftCardsByPurchasedWithOrderItemIdAsync`: Retrieves gift cards based on the purchased with order item identifier.
- `GetActiveGiftCardsAppliedByCustomerAsync`: Retrieves active gift cards applied by a customer.
- `GenerateGiftCardCode`: Generates a new gift card code.
- `DeleteGiftCardUsageHistoryAsync`: Deletes gift card usage history.
- `GetGiftCardRemainingAmountAsync`: Retrieves the remaining amount of a gift card.
- `GetGiftCardUsageHistoryAsync`: Retrieves gift card usage history entries.
- `InsertGiftCardUsageHistoryAsync`: Inserts a new gift card usage history entry.
- `IsGiftCardValidAsync`: Checks if a gift card is valid.
___
### Fields
- `_customerService`: An instance of the `ICustomerService` interface.
- `_eventPublisher`: An instance of the `IEventPublisher` interface.
- `_giftCardRepository`: An instance of the `IRepository<GiftCard>` interface.
- `_giftCardUsageHistoryRepository`: An instance of the `IRepository<GiftCardUsageHistory>` interface.
- `_orderItemRepository`: An instance of the `IRepository<OrderItem>` interface.
___
