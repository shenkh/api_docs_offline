<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.errors" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="ABORTED"/>
<meta itemprop="property" content="ALREADY_EXISTS"/>
<meta itemprop="property" content="CANCELLED"/>
<meta itemprop="property" content="DATA_LOSS"/>
<meta itemprop="property" content="DEADLINE_EXCEEDED"/>
<meta itemprop="property" content="FAILED_PRECONDITION"/>
<meta itemprop="property" content="INTERNAL"/>
<meta itemprop="property" content="INVALID_ARGUMENT"/>
<meta itemprop="property" content="NOT_FOUND"/>
<meta itemprop="property" content="OK"/>
<meta itemprop="property" content="OUT_OF_RANGE"/>
<meta itemprop="property" content="PERMISSION_DENIED"/>
<meta itemprop="property" content="RESOURCE_EXHAUSTED"/>
<meta itemprop="property" content="UNAUTHENTICATED"/>
<meta itemprop="property" content="UNAVAILABLE"/>
<meta itemprop="property" content="UNIMPLEMENTED"/>
<meta itemprop="property" content="UNKNOWN"/>
</div>

# Module: tf.errors



Defined in [`tensorflow/_api/v1/errors/__init__.py`](/code/stable/tensorflow/_api/v1/errors/__init__.py).

Exception types for TensorFlow errors.

## Classes

[`class AbortedError`](../tf/errors/AbortedError.md): The operation was aborted, typically due to a concurrent action.

[`class AlreadyExistsError`](../tf/errors/AlreadyExistsError.md): Raised when an entity that we attempted to create already exists.

[`class CancelledError`](../tf/errors/CancelledError.md): Raised when an operation or step is cancelled.

[`class DataLossError`](../tf/errors/DataLossError.md): Raised when unrecoverable data loss or corruption is encountered.

[`class DeadlineExceededError`](../tf/errors/DeadlineExceededError.md): Raised when a deadline expires before an operation could complete.

[`class FailedPreconditionError`](../tf/errors/FailedPreconditionError.md): Operation was rejected because the system is not in a state to execute it.

[`class InternalError`](../tf/errors/InternalError.md): Raised when the system experiences an internal error.

[`class InvalidArgumentError`](../tf/errors/InvalidArgumentError.md): Raised when an operation receives an invalid argument.

[`class NotFoundError`](../tf/errors/NotFoundError.md): Raised when a requested entity (e.g., a file or directory) was not found.

[`class OpError`](../tf/errors/OpError.md): A generic error that is raised when TensorFlow execution fails.

[`class OutOfRangeError`](../tf/errors/OutOfRangeError.md): Raised when an operation iterates past the valid input range.

[`class PermissionDeniedError`](../tf/errors/PermissionDeniedError.md): Raised when the caller does not have permission to run an operation.

[`class ResourceExhaustedError`](../tf/errors/ResourceExhaustedError.md): Some resource has been exhausted.

[`class UnauthenticatedError`](../tf/errors/UnauthenticatedError.md): The request does not have valid authentication credentials.

[`class UnavailableError`](../tf/errors/UnavailableError.md): Raised when the runtime is currently unavailable.

[`class UnimplementedError`](../tf/errors/UnimplementedError.md): Raised when an operation has not been implemented.

[`class UnknownError`](../tf/errors/UnknownError.md): Unknown error.

[`class raise_exception_on_not_ok_status`](../tf/errors/raise_exception_on_not_ok_status.md): Context manager to check for C API status.

## Functions

[`error_code_from_exception_type(...)`](../tf/errors/error_code_from_exception_type.md)

[`exception_type_from_error_code(...)`](../tf/errors/exception_type_from_error_code.md)

## Other Members

<h3 id="ABORTED"><code>ABORTED</code></h3>

<h3 id="ALREADY_EXISTS"><code>ALREADY_EXISTS</code></h3>

<h3 id="CANCELLED"><code>CANCELLED</code></h3>

<h3 id="DATA_LOSS"><code>DATA_LOSS</code></h3>

<h3 id="DEADLINE_EXCEEDED"><code>DEADLINE_EXCEEDED</code></h3>

<h3 id="FAILED_PRECONDITION"><code>FAILED_PRECONDITION</code></h3>

<h3 id="INTERNAL"><code>INTERNAL</code></h3>

<h3 id="INVALID_ARGUMENT"><code>INVALID_ARGUMENT</code></h3>

<h3 id="NOT_FOUND"><code>NOT_FOUND</code></h3>

<h3 id="OK"><code>OK</code></h3>

<h3 id="OUT_OF_RANGE"><code>OUT_OF_RANGE</code></h3>

<h3 id="PERMISSION_DENIED"><code>PERMISSION_DENIED</code></h3>

<h3 id="RESOURCE_EXHAUSTED"><code>RESOURCE_EXHAUSTED</code></h3>

<h3 id="UNAUTHENTICATED"><code>UNAUTHENTICATED</code></h3>

<h3 id="UNAVAILABLE"><code>UNAVAILABLE</code></h3>

<h3 id="UNIMPLEMENTED"><code>UNIMPLEMENTED</code></h3>

<h3 id="UNKNOWN"><code>UNKNOWN</code></h3>

