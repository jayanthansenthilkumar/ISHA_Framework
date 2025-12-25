# Changelog

All notable changes to the ISHA Framework will be documented in this file.

## [0.2.0] - 2025-12-25

### Added

#### Core Enhancements
- **URL Parameters (Dynamic Routes)**: Routes can now include dynamic parameters using `{param}` syntax (e.g., `/users/{id}`)
  - Automatic regex-based pattern matching
  - Multiple parameters per route supported
  - Parameters accessible via `req.params` dictionary

- **JSON Body Parsing**: Automatic parsing of JSON request bodies
  - Detects `Content-Type: application/json`
  - Parsed data available as `req.json_body`
  - Safe parsing with `None` fallback on errors

#### New Modules

- **`isha/cors.py`**: Full CORS (Cross-Origin Resource Sharing) support
  - `CORS` class for manual configuration
  - `enable_cors()` function for quick setup
  - Automatic preflight request handling
  - Configurable origins, methods, headers, and credentials

- **`isha/uploads.py`**: File upload handling
  - `UploadedFile` class with metadata (filename, size, content_type)
  - `FileUploadHandler` middleware for automatic processing
  - `parse_multipart()` function for manual parsing
  - File size limits and automatic directory creation
  - Simple `.save()` API

- **`isha/ratelimit.py`**: Rate limiting protection
  - `RateLimiter` class with token bucket algorithm
  - `RouteRateLimiter` for per-route limits
  - `enable_rate_limiting()` for global limits
  - Per-IP tracking
  - Configurable burst capacity
  - Returns 429 status when limit exceeded

- **`isha/cache.py`**: Response caching
  - `Cache` class for general-purpose caching
  - `ResponseCache` for HTTP response caching
  - `@cached_route` decorator for easy route caching
  - TTL-based expiration
  - LRU eviction when max size reached
  - Manual cache control (get, set, delete, clear)

- **`isha/logger.py`**: Structured logging
  - `Logger` class with colored output
  - Five log levels: DEBUG, INFO, WARNING, ERROR, CRITICAL
  - `RequestLogger` for automatic HTTP logging
  - `enable_request_logging()` convenience function
  - Contextual logging with metadata
  - Duration tracking for requests

#### New Demo Application
- **`demo_enhanced.pyisha`**: Comprehensive demo showcasing all new features
  - 15+ routes demonstrating URL parameters, JSON APIs, file uploads
  - Modern responsive UI with gradient design
  - Database-backed examples
  - Upload tracking system
  - Complete error handling

#### Documentation
- **`NEW_FEATURES.md`**: Complete guide to all new features with examples
- **`QUICK_REFERENCE.md`**: Quick reference guide for common patterns
- **`ENHANCEMENT_SUMMARY.md`**: Detailed summary of changes and statistics
- **`CHANGELOG.md`**: This file
- Updated **`README.md`** with new features section

### Changed
- Updated `__init__.py` to export all new modules and functions
- Bumped version from 0.1.0 to 0.2.0
- Enhanced `Request` class with `json_body` and `params` attributes
- Enhanced `App` class with `dynamic_routes` list and `_match_dynamic_route()` method

### Statistics
- Added 5 new modules (~950 lines of code)
- Enhanced 2 existing modules (core.py, __init__.py)
- Created 1 comprehensive demo application
- Added 4 new documentation files
- Total feature count increased from 11 to 18

### Compatibility
- **No breaking changes** - All new features are opt-in
- Existing applications continue to work without modification
- Still maintains zero external dependencies

---

## [0.1.0] - 2025-12-24

### Added
- Initial release
- Core framework (App, Request, Response)
- HTTP server with socket-based implementation
- `.pyisha` file loader
- CLI with `isha run` command
- Configuration management
- SQLite database wrapper
- HTML template engine
- Static file serving
- Cookie-based sessions
- Form validation
- Middleware support (before/after request)
- Error handlers
- JSON response support
- Query parameter parsing

### Features
- Zero external dependencies
- Pure Python implementation
- Custom file extension (`.pyisha`)
- Clean routing system
- Professional developer experience

---

## Future Roadmap

Potential features for future releases:
- WebSocket support
- GraphQL endpoint handling
- Background task queues
- Database migrations
- Authentication/authorization helpers
- API versioning
- Request validation schemas
- Response compression
- Template inheritance
- ORM capabilities
- Email sending
- PDF generation
- Excel file handling
- And more...

---

[0.2.0]: https://github.com/isha-framework/isha/releases/tag/v0.2.0
[0.1.0]: https://github.com/isha-framework/isha/releases/tag/v0.1.0
