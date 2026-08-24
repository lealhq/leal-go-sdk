# Reference
## Stores
<details><summary><code>client.Stores.List() -> []*leal.ListStoresResponseItem</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns every store the authenticated user has access to, including summary counts for locations, cards, customers, and posters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Stores.List(
    context.TODO(),
)
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Stores.Get(ID) -> *leal.GetStoresResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns detailed information for a single store, including summary counts for its associated resources.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.GetStoresRequest{
    ID: 1,
}
client.Stores.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Store ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Stores.Update(ID, request) -> *leal.UpdateStoresResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the store's name or store_name. Use `store_name` for the public-facing name displayed to customers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.UpdateStoresRequest{
    ID: 1,
    Account: &leal.UpdateStoresRequestAccount{},
}
client.Stores.Update(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Store ID
    
</dd>
</dl>

<dl>
<dd>

**account:** `*leal.UpdateStoresRequestAccount` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Cards
<details><summary><code>client.Cards.List(AccountID) -> []*leal.ListCardsResponseItem</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns loyalty card templates for the specified store. By default, only
active (unarchived) cards are returned. Use the `scope` parameter to include
archived cards.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.ListCardsRequest{
    AccountID: 1,
}
client.Cards.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**scope:** `*string` — Filter cards by archive status. Default: active only.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Cards.Create(AccountID, request) -> *leal.CreateCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new loyalty stamp card template for the store. The card defines the
visual design (colours, icon, strip) and program rules (stamps required,
initial stamps).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.CreateCardsRequest{
    AccountID: 1,
    Card: &leal.CreateCardsRequestCard{
        Name: "name",
    },
}
client.Cards.Create(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**card:** `*leal.CreateCardsRequestCard` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Cards.Get(AccountID, ID) -> *leal.GetCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single loyalty card template by ID, including reward and customer card counts.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.GetCardsRequest{
    AccountID: 1,
    ID: 1,
}
client.Cards.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Card ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Cards.Update(AccountID, ID, request) -> *leal.UpdateCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing loyalty card template. Only the provided attributes are changed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.UpdateCardsRequest{
    AccountID: 1,
    ID: 1,
    Card: &leal.UpdateCardsRequestCard{},
}
client.Cards.Update(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Card ID
    
</dd>
</dl>

<dl>
<dd>

**card:** `*leal.UpdateCardsRequestCard` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Customers
<details><summary><code>client.Customers.List(AccountID) -> *leal.ListCustomersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated list of customers for the store. Use the `search` parameter to filter
by name, email, phone, card code (barcode), or external reference ID. Alternatively, pass
`source` AND `external_id` together to perform an exact lookup by an external reference -
the response will contain at most one customer.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.ListCustomersRequest{
    AccountID: 1,
}
client.Customers.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**search:** `*string` — Search query to filter customers by name, email, phone, card code (barcode), or external reference ID
    
</dd>
</dl>

<dl>
<dd>

**source:** `*string` — External system slug (e.g. `square`, `shopify`). When combined with `external_id`, performs an exact lookup.
    
</dd>
</dl>

<dl>
<dd>

**externalID:** `*string` — External system's identifier for the customer. Must be combined with `source`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number (defaults to 1)
    
</dd>
</dl>

<dl>
<dd>

**items:** `*int` — Number of items per page
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Customers.Create(AccountID, request) -> *leal.CreateCustomersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new customer for the store. Requires `first_name` and at least one of `email` or `phone`.
Optionally enroll the customer in a loyalty card by passing `card_id`, and trigger delivery of
card links (email/SMS) by passing `send_card_links`. When a card with initial stamps is assigned,
those stamps are automatically applied as a welcome bonus.

Pass `metadata` to attach arbitrary key/value data, and `external_references` to link the
customer to records in other systems (e.g. Square, Shopify). External references are upserted
by `(source, external_id)` so this endpoint is safe to call with the same references twice.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.CreateCustomersRequest{
    AccountID: 1,
    Customer: &leal.CreateCustomersRequestCustomer{
        FirstName: "first_name",
    },
}
client.Customers.Create(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**cardID:** `*int` — Loyalty card ID to auto-enroll the customer in
    
</dd>
</dl>

<dl>
<dd>

**customer:** `*leal.CreateCustomersRequestCustomer` 
    
</dd>
</dl>

<dl>
<dd>

**sendCardLinks:** `*bool` — When true, sends the card links to the customer via email/SMS after enrollment. Note: even without this flag, the response includes `apple_wallet_url` and `google_wallet_url` in each customer card object so you can deliver them yourself.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Customers.Get(AccountID, ID) -> *leal.GetCustomersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns detailed information about a single customer, including all of their
enrolled loyalty cards with stamp progress and wallet pass URLs (`apple_wallet_url`
and `google_wallet_url`) for each card. Also includes `metadata` and
`external_references` so you can sync state with external systems.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.GetCustomersRequest{
    AccountID: 1,
    ID: 1,
}
client.Customers.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Customers.Update(AccountID, ID, request) -> *leal.UpdateCustomersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing customer's details. To add stamps or redeem rewards, use the
customer cards endpoints instead.

`metadata` is shallow-merged into the existing metadata. `external_references` are upserted
by `(source, external_id)` - to remove a reference, omit it from subsequent calls and use
a separate `DELETE` workflow (not yet exposed via API; manage in dashboard for now).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.UpdateCustomersRequest{
    AccountID: 1,
    ID: 1,
    Customer: &leal.UpdateCustomersRequestCustomer{},
}
client.Customers.Update(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**customer:** `*leal.UpdateCustomersRequestCustomer` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Customer Cards
<details><summary><code>client.CustomerCards.List(AccountID, CustomerID) -> []*leal.ListCustomerCardsResponseItem</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all loyalty cards enrolled for a specific customer, including stamp progress,
status, wallet pass installation state, and wallet pass URLs (`apple_wallet_url` and
`google_wallet_url`) that you can use to let customers add their loyalty card to
Apple Wallet or Google Wallet from your own app or website.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.ListCustomerCardsRequest{
    AccountID: 1,
    CustomerID: 1,
}
client.CustomerCards.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customerID:** `int` — Customer ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.CustomerCards.Get(AccountID, CustomerID, ID) -> *leal.GetCustomerCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns detailed information about a specific customer card, including stamp progress,
a list of rewards the customer has earned enough stamps to redeem, and wallet pass URLs
(`apple_wallet_url` and `google_wallet_url`) for adding the card to Apple Wallet or
Google Wallet.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.GetCustomerCardsRequest{
    AccountID: 1,
    CustomerID: 1,
    ID: 1,
}
client.CustomerCards.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customerID:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer card ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.CustomerCards.Redeem(AccountID, CustomerID, ID, request) -> *leal.RedeemCustomerCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Redeems a reward for a customer, deducting the required stamps from their card.
The customer must have enough stamps on this card to cover the reward's cost.
Triggers wallet pass updates and push notifications.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.RedeemCustomerCardsRequest{
    AccountID: 1,
    CustomerID: 1,
    ID: 1,
    RewardID: 1,
}
client.CustomerCards.Redeem(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customerID:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer card ID
    
</dd>
</dl>

<dl>
<dd>

**rewardID:** `int` — Reward ID to redeem
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.CustomerCards.Stamp(AccountID, CustomerID, ID, request) -> *leal.StampCustomerCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Adds stamps to a customer's loyalty card. Triggers ledger entries, wallet pass updates,
and push notifications. Pass `skip_notifications` to stamp silently.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.StampCustomerCardsRequest{
    AccountID: 1,
    CustomerID: 1,
    ID: 1,
    Stamps: 1,
}
client.CustomerCards.Stamp(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customerID:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer card ID
    
</dd>
</dl>

<dl>
<dd>

**skipNotifications:** `*bool` — When true, stamp changes bypass notifications
    
</dd>
</dl>

<dl>
<dd>

**stamps:** `int` — Number of stamps to add (e.g. 1, 3)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Locations
<details><summary><code>client.Locations.List(AccountID) -> []*leal.ListLocationsResponseItem</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns every physical location belonging to the specified store.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.ListLocationsRequest{
    AccountID: 1,
}
client.Locations.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Locations.Create(AccountID, request) -> *leal.CreateLocationsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new physical location for the store. The provided address is
automatically geocoded to latitude and longitude coordinates in the background.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.CreateLocationsRequest{
    AccountID: 1,
    Location: &leal.CreateLocationsRequestLocation{
        Address: "address",
        Name: "name",
    },
}
client.Locations.Create(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**location:** `*leal.CreateLocationsRequestLocation` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Locations.Get(AccountID, ID) -> *leal.GetLocationsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single location by ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.GetLocationsRequest{
    AccountID: 1,
    ID: 1,
}
client.Locations.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Location ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Locations.Delete(AccountID, ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently deletes a location. This action cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.DeleteLocationsRequest{
    AccountID: 1,
    ID: 1,
}
client.Locations.Delete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Location ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Locations.Update(AccountID, ID, request) -> *leal.UpdateLocationsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing location. If the address is changed, it will be re-geocoded automatically.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.UpdateLocationsRequest{
    AccountID: 1,
    ID: 1,
    Location: &leal.UpdateLocationsRequestLocation{},
}
client.Locations.Update(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Location ID
    
</dd>
</dl>

<dl>
<dd>

**location:** `*leal.UpdateLocationsRequestLocation` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Posters
<details><summary><code>client.Posters.List(AccountID) -> []*leal.ListPostersResponseItem</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all posters for the store. Optionally filter by card or active status.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.ListPostersRequest{
    AccountID: 1,
}
client.Posters.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**cardID:** `*int` — Filter posters belonging to a specific card
    
</dd>
</dl>

<dl>
<dd>

**active:** `*string` — When present, return only active posters
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Posters.Create(AccountID, request) -> *leal.CreatePostersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new printable QR code poster for customer signup. The poster will automatically
generate a unique public signup URL and QR code. The `card_id` is required on create to
associate the poster with a loyalty card.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.CreatePostersRequest{
    AccountID: 1,
    Poster: &leal.CreatePostersRequestPoster{
        CardID: 1,
    },
}
client.Posters.Create(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**poster:** `*leal.CreatePostersRequestPoster` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Posters.Get(AccountID, ID) -> *leal.GetPostersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single poster by ID, including generated signup and display URLs.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.GetPostersRequest{
    AccountID: 1,
    ID: 1,
}
client.Posters.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Poster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Posters.Delete(AccountID, ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently deletes a poster. The public signup URL will stop working.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.DeletePostersRequest{
    AccountID: 1,
    ID: 1,
}
client.Posters.Delete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Poster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Posters.Update(AccountID, ID, request) -> *leal.UpdatePostersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing poster. The `card_id` cannot be changed after creation.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.UpdatePostersRequest{
    AccountID: 1,
    ID: 1,
    Poster: &leal.UpdatePostersRequestPoster{},
}
client.Posters.Update(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Poster ID
    
</dd>
</dl>

<dl>
<dd>

**poster:** `*leal.UpdatePostersRequestPoster` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Rewards
<details><summary><code>client.Rewards.List(AccountID) -> []*leal.ListRewardsResponseItem</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all rewards for the store. Optionally filter by card or active status.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.ListRewardsRequest{
    AccountID: 1,
}
client.Rewards.List(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**cardID:** `*int` — Filter rewards belonging to a specific card
    
</dd>
</dl>

<dl>
<dd>

**active:** `*string` — When present, return only active rewards
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Rewards.Create(AccountID, request) -> *leal.CreateRewardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new reward for a loyalty card. The card must belong to the same store.
The `card_id` is required on create but cannot be changed afterwards.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.CreateRewardsRequest{
    AccountID: 1,
    Reward: &leal.CreateRewardsRequestReward{
        CardID: 1,
        Name: "name",
        StampsRequired: 1,
    },
}
client.Rewards.Create(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**reward:** `*leal.CreateRewardsRequestReward` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Rewards.Get(AccountID, ID) -> *leal.GetRewardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single reward by ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.GetRewardsRequest{
    AccountID: 1,
    ID: 1,
}
client.Rewards.Get(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Reward ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Rewards.Delete(AccountID, ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently deletes a reward. This cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.DeleteRewardsRequest{
    AccountID: 1,
    ID: 1,
}
client.Rewards.Delete(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Reward ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Rewards.Update(AccountID, ID, request) -> *leal.UpdateRewardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing reward. The `card_id` cannot be changed after creation.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &leal.UpdateRewardsRequest{
    AccountID: 1,
    ID: 1,
    Reward: &leal.UpdateRewardsRequestReward{},
}
client.Rewards.Update(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**accountID:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Reward ID
    
</dd>
</dl>

<dl>
<dd>

**reward:** `*leal.UpdateRewardsRequestReward` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Status
<details><summary><code>client.Status.Check() -> *leal.CheckStatusResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the status of the API. No authentication required.

Every response from this API, including this one, carries `RateLimit-Limit`,
`RateLimit-Remaining`, `RateLimit-Reset` and `RateLimit-Policy`. Exceeding
the limit returns 429 with `Retry-After` in seconds.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Status.Check(
    context.TODO(),
)
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

