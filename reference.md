# Reference
## Quotes
<details><summary><code>client.quotes.showQuote(id) -> QuoteResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.quotes().showQuote(
    1,
    GetQuoteRequestsIdRequest
        .builder()
        .build()
);
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

**id:** `Integer` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.quotes.deleteQuote(id) -> DeleteQuoteRequestsIdResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.quotes().deleteQuote(
    1,
    DeleteQuoteRequestsIdRequest
        .builder()
        .build()
);
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

**id:** `Integer` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.quotes.listQuotes() -> GetQuoteRequestsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.quotes().listQuotes();
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.quotes.requestQuotes(request) -> QuoteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

For getting prices with benefits. 
The Quote IDs can be used later to issue a policy
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.quotes().requestQuotes(
    PostQuoteRequestsRequest
        .builder()
        .ownerId("owner_id")
        .phone("phone")
        .birthdate("2023-01-15")
        .carSequenceNumber("car_sequence_number")
        .carEstimatedCost(1.1)
        .build()
);
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

**ownerId:** `String` — Owner ID must be 10 digits starting with 1, 2, or 7
    
</dd>
</dl>

<dl>
<dd>

**email:** `Optional<String>` — Email address must be valid and belongs to the customer
    
</dd>
</dl>

<dl>
<dd>

**phone:** `String` — Phone number must start with 05 and be 10 digits
    
</dd>
</dl>

<dl>
<dd>

**birthdate:** `String` — Birthdate in YYYY-MM-DD format
    
</dd>
</dl>

<dl>
<dd>

**carSequenceNumber:** `String` — Car sequence number must be 8 or 9 digits
    
</dd>
</dl>

<dl>
<dd>

**isOwnershipTransfer:** `Optional<Boolean>` — Indicates if the ownership is being transferred
    
</dd>
</dl>

<dl>
<dd>

**currentCarOwnerId:** `Optional<String>` — Required if is_ownership_transfer is true; 10 digits starting with 1,2,7
    
</dd>
</dl>

<dl>
<dd>

**carEstimatedCost:** `Double` — Estimated cost of the car
    
</dd>
</dl>

<dl>
<dd>

**carModelYear:** `Optional<Integer>` — Car model year between 1950 and next year
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `Optional<String>` — Desired policy start date in YYYY-MM-DD. Must be between tomorrow and 28 days from today (inclusive). The platform validates this range server-side.
    
</dd>
</dl>

<dl>
<dd>

**drivers:** `Optional<List<PostQuoteRequestsRequestDriversItem>>` — List of drivers for the vehicle. When provided, the sum of all driving_percentage values must equal 100, and the owner must be included among the drivers.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Policies
<details><summary><code>client.policies.showPolicy(carPolicy) -> Policy</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Show a specific policy
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.policies().showPolicy(
    1,
    GetPoliciesCarPolicyRequest
        .builder()
        .build()
);
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

**carPolicy:** `Integer` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.policies.listPolicies() -> List&amp;lt;Policy&amp;gt;</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Listing requested policies
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.policies().listPolicies(
    GetPoliciesRequest
        .builder()
        .build()
);
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

**quoteRequestId:** `Optional<Integer>` 
    
</dd>
</dl>

<dl>
<dd>

**quotePriceId:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**providerPolicyId:** `Optional<Integer>` 
    
</dd>
</dl>

<dl>
<dd>

**carSequenceNumber:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**newOwnerId:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**previousOwnerId:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `Optional<Integer>` 
    
</dd>
</dl>

<dl>
<dd>

**minPrice:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**maxPrice:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**perPage:** `Optional<Integer>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.policies.issuePolicy(request) -> Policy</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

For issuing a new policy
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.policies().issuePolicy(
    PostPoliciesRequest
        .builder()
        .quoteRequestId(123)
        .quoteReferenceId("550e8400-e29b-41d4-a716-446655440000")
        .quotePriceId("550e8400-e29b-41d4-a716-446655440001")
        .build()
);
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

**quoteRequestId:** `Integer` — ID of the car quote request
    
</dd>
</dl>

<dl>
<dd>

**quoteReferenceId:** `String` — Unique identifier for the quote reference ID (coming from POST /quote-requests)
    
</dd>
</dl>

<dl>
<dd>

**quotePriceId:** `String` — Unique identifier for the quote price ID that exists inside a quote item (coming from POST /quote-requests)
    
</dd>
</dl>

<dl>
<dd>

**benefits:** `Optional<List<String>>` — List of benefit UUIDs
    
</dd>
</dl>

<dl>
<dd>

**extraFields:** `Optional<Map<String, Object>>` — Optional free-form object with additional fields. Total JSON-encoded size must not exceed 255 characters.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## OtPs
<details><summary><code>client.otPs.requestOtpForQuoteVerification(request)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This endpoint sends a one-time password (OTP) to the provided email and phone number for quote verification. It should be called before creating a quote request.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.otPs().requestOtpForQuoteVerification(
    PostQuoteOtpRequest
        .builder()
        .email("someone@example.com")
        .phone("0501234567")
        .ownerId("1012345678")
        .build()
);
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

**email:** `String` — Email address of the car owner
    
</dd>
</dl>

<dl>
<dd>

**phone:** `String` — Phone number starting with 05 and containing 10 digits
    
</dd>
</dl>

<dl>
<dd>

**ownerId:** `String` — National ID or Iqama ID of the car owner (10 digits)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.otPs.requestOtpForIssuingPolicy(request)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This endpoint sends a one-time password (OTP). It should be called before issuing a policy.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.otPs().requestOtpForIssuingPolicy(
    PostIssueOtpRequest
        .builder()
        .email("someone@example.com")
        .phone("0501234567")
        .ownerId("1012345678")
        .quoteRequestId(123)
        .quoteReferenceId("550e8400-e29b-41d4-a716-446655440000")
        .quotePriceId("550e8400-e29b-41d4-a716-446655440001")
        .build()
);
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

**email:** `String` — Email address of the car owner
    
</dd>
</dl>

<dl>
<dd>

**phone:** `String` — Phone number starting with 05 and containing 10 digits
    
</dd>
</dl>

<dl>
<dd>

**ownerId:** `String` — National ID or Iqama ID of the car owner (10 digits)
    
</dd>
</dl>

<dl>
<dd>

**quoteRequestId:** `Integer` — ID of the car quote request
    
</dd>
</dl>

<dl>
<dd>

**quoteReferenceId:** `String` — Unique identifier for the quote reference ID (coming from POST /quote-requests)
    
</dd>
</dl>

<dl>
<dd>

**quotePriceId:** `String` — Unique identifier for the quote price ID that exists inside a quote item (coming from POST /quote-requests)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

