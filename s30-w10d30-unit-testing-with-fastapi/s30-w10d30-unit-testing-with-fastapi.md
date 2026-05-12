# Course Outline: Unit Testing with FastAPI

**Title:** Unit Testing with FastAPI
**Learnpack:** + Unit testing with FastAPI
**Prerequisite:** Introduction to FastAPI, Debugging with Python, Introducción al testing
**Target Audience:** Beginner developers building FastAPI applications who need to implement comprehensive testing strategies
**Total Lessons:** 10
**Format:** Mixed (40% hands-on)

---

## Course Description

This course teaches students how to implement robust unit testing for FastAPI applications using Python's most popular testing frameworks. Students will master unittest, pytest, and doctest, learning when and how to use each framework effectively. The course emphasizes practical test planning strategies, covering edge cases, and building maintainable test suites that integrate seamlessly with FastAPI's architecture.

Building on previous knowledge of FastAPI fundamentals and basic testing concepts, this course focuses specifically on testing web API endpoints, request/response cycles, and CRUD operations. Students will develop the skills to plan comprehensive test coverage and implement test-driven development practices in their FastAPI projects.

---

## Course Philosophy

This course emphasizes:
- **Test-first thinking**: Planning tests before implementation to ensure comprehensive coverage
- **Framework mastery**: Understanding when to use unittest, pytest, or doctest for different testing scenarios
- **Practical application**: Testing real FastAPI endpoints and components, not abstract examples
- **Quality over quantity**: Writing meaningful tests that catch real bugs, avoiding test bloat

---

## Course Statistics Summary

| Section | Lessons |
|---------|---------|
| 00 - Welcome | 1 |
| 01 - Testing Framework Fundamentals | 3 |
| 02 - FastAPI Testing Essentials | 3 |
| 03 - Test Planning and Strategy | 2 |
| 04 - Assessment and Mastery | 2 |
| 05 - Outro | 1 |
| **Total** | **10** |

---

## Section 00: Welcome

### 00.0 Welcome to FastAPI Testing 📖

**Learning Objectives:**
- Understand the critical role of testing in FastAPI application development
- Identify the unique testing challenges that FastAPI applications present
- Preview the testing frameworks and strategies covered in this course
- Recognize how this course builds on previous testing and FastAPI knowledge

**Content Outline:**
- Why FastAPI applications need comprehensive testing strategies
- The testing landscape: unittest, pytest, doctest for different scenarios
- Preview of test planning methodologies and TDD with FastAPI
- Course roadmap and expected outcomes

**Transitions:**
This lesson establishes the foundation for our deep dive into Python testing frameworks, starting with understanding each framework's strengths and use cases.

**Key Principles:**
- Testing FastAPI applications requires understanding both the framework's architecture and Python testing tools
- Different testing scenarios call for different testing frameworks
- Comprehensive test planning prevents gaps in coverage
- Testing should integrate seamlessly with FastAPI's development workflow

**Examples:**
- A FastAPI endpoint that works in simple cases but fails with edge case data
- Comparison of testing the same functionality with unittest vs pytest vs doctest
- Real-world scenario where inadequate testing led to production API failures

---

## Section 01: Testing Framework Fundamentals

### 01.0 Python Testing Frameworks: unittest, pytest, doctest 📖

**Learning Objectives:**
- Compare and contrast unittest, pytest, and doctest frameworks
- Understand when to choose each framework for different testing scenarios
- Recognize the syntax and structural differences between frameworks
- Identify framework-specific advantages for FastAPI testing

**Content Outline:**
- unittest: Python's built-in testing framework - structure, assertions, and setup/teardown
- pytest: Third-party powerhouse - fixtures, parametrization, and plugin ecosystem
- doctest: Documentation-driven testing - embedding tests in docstrings
- Framework comparison matrix: when to use each for FastAPI components
- Integration considerations with FastAPI's dependency injection and async nature

**Transitions:**
Now that we understand each framework's characteristics, let's set up our first testing environment and establish best practices.

**Key Principles:**
- unittest provides robust structure for complex test suites but requires more boilerplate
- pytest offers powerful features and concise syntax ideal for API endpoint testing
- doctest excels for testing individual functions and providing executable documentation
- Framework choice should align with testing goals and team preferences

**Examples:**
- The same FastAPI utility function tested with all three frameworks
- pytest fixtures vs unittest setUp methods for database connections
- doctest embedded in a FastAPI model validation function

**Anti-patterns (woven in):**
- **Framework mixing without purpose**: Using multiple frameworks in the same test suite without clear architectural reasons creates confusion and maintenance overhead. Choose one primary framework per project.
- **Ignoring async testing**: Treating FastAPI's async endpoints like synchronous functions in tests leads to incomplete coverage and false confidence.

---

### 01.1 Setting Up Your First Test Environment 📖

**Learning Objectives:**
- Configure testing environments for unittest, pytest, and doctest with FastAPI
- Understand TestClient and its role in FastAPI testing
- Set up proper project structure for organized test suites
- Configure testing databases and mock dependencies

**Content Outline:**
- Project structure: organizing tests/, conftest.py, and test discovery
- Installing and configuring pytest with FastAPI dependencies
- FastAPI's TestClient: creating isolated test environments
- Database setup for testing: in-memory databases and test fixtures
- Environment variable management for testing vs production
- Running tests: command line options and IDE integration

**Transitions:**
With our environment configured, we're ready to write our first tests using each framework to understand their practical differences.

**Key Principles:**
- Test isolation: each test should run independently without side effects
- Test organization: clear structure makes test suites maintainable and discoverable
- TestClient provides FastAPI-specific testing capabilities beyond standard HTTP clients
- Testing configuration should mirror production structure while remaining fast and isolated

**Examples:**
- Directory structure for a FastAPI project with comprehensive test organization
- conftest.py setup with database fixtures and TestClient configuration
- Environment variable configuration for different testing scenarios

**Anti-patterns (woven in):**
- **Production database testing**: Running tests against production or shared databases risks data corruption and creates unreliable tests. Always use isolated test databases.
- **Slow test setup**: Complex test environment setup that takes minutes to run discourages frequent testing. Keep setup lean and fast.

---

### 01.2 Writing Basic Tests with Each Framework 💻

**Challenge Prompt:**
Create a simple FastAPI endpoint that returns user information, then write identical tests for this endpoint using unittest, pytest, and doctest frameworks to demonstrate their different syntaxes and approaches.

**Solution Code:**
```python
# app.py - FastAPI endpoint
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class User(BaseModel):
    id: int
    name: str
    email: str

@app.get("/users/{user_id}")
async def get_user(user_id: int):
    """Get user by ID.
    
    >>> # doctest example
    >>> user = get_user(1)
    >>> user.id
    1
    >>> user.name
    'John Doe'
    """
    return User(id=user_id, name="John Doe", email="john@example.com")

# test_frameworks.py - All three testing approaches
import unittest
import pytest
import doctest
from fastapi.testclient import TestClient
from app import app, get_user

client = TestClient(app)

# unittest approach
class TestUserEndpoint(unittest.TestCase):
    def test_get_user_unittest(self):
        response = client.get("/users/1")
        self.assertEqual(response.status_code, 200)
        self.assertEqual(response.json()["name"], "John Doe")

# pytest approach
def test_get_user_pytest():
    response = client.get("/users/1")
    assert response.status_code == 200
    assert response.json()["name"] == "John Doe"

# doctest runner
if __name__ == "__main__":
    doctest.testmod()
```

**Challenge Code:**
```python
# app.py - FastAPI endpoint (starter)
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class User(BaseModel):
    id: int
    name: str
    email: str

@app.get("/users/{user_id}")
async def get_user(user_id: int):
    """Get user by ID.
    
    # Add doctest example here
    """
    # Return user data
    pass

# test_frameworks.py - Write tests using all frameworks
import unittest
import pytest
import doctest
from fastapi.testclient import TestClient
from app import app, get_user

client = TestClient(app)

# unittest approach
class TestUserEndpoint(unittest.TestCase):
    def test_get_user_unittest(self):
        # Write unittest test here
        pass

# pytest approach  
def test_get_user_pytest():
    # Write pytest test here
    pass

# doctest runner
if __name__ == "__main__":
    # Run doctest
    pass
```

---

## Section 02: FastAPI Testing Essentials

### 02.0 Unit Testing FastAPI Endpoints and Components 📖

**Learning Objectives:**
- Apply testing frameworks specifically to FastAPI endpoints and middleware
- Understand TestClient capabilities for comprehensive API testing
- Test FastAPI dependency injection and async operations
- Implement proper mocking strategies for external dependencies

**Content Outline:**
- TestClient deep dive: request simulation, headers, authentication
- Testing different HTTP methods: GET, POST, PUT, DELETE with proper assertions
- Async testing patterns: handling coroutines and async dependencies
- Dependency injection testing: overriding dependencies for isolated tests
- Testing FastAPI middleware and exception handlers
- Response validation: status codes, headers, JSON structure, and Pydantic models

**Transitions:**
Building on endpoint testing fundamentals, we'll now explore comprehensive CRUD operation testing and request/response cycle validation.

**Key Principles:**
- FastAPI's TestClient handles async/await automatically for synchronous test code
- Dependency overrides enable testing without external services or databases
- Response testing should validate both structure and business logic
- Middleware and exception handlers need separate testing strategies

**Examples:**
- Testing a protected endpoint with authentication dependency override
- Async endpoint test with database operations using test fixtures
- Middleware testing for request/response modification

**Anti-patterns (woven in):**
- **Testing only happy paths**: Only testing successful responses ignores error handling and edge cases that users will encounter. Always include error scenario tests.
- **Overreliance on integration tests**: Testing entire request flows without unit testing individual components makes debugging failures difficult and tests slow.

---

### 02.1 Testing CRUD Operations and Request/Response Cycles 📖

**Learning Objectives:**
- Design comprehensive tests for Create, Read, Update, Delete operations
- Validate request parsing, data transformation, and response formatting
- Test error scenarios: validation failures, missing resources, authorization
- Implement data-driven testing for multiple input scenarios

**Content Outline:**
- CRUD testing patterns: setup, execution, assertion, cleanup
- Request body validation: testing Pydantic model parsing and validation errors
- Response serialization testing: ensuring proper JSON output format
- Error response testing: 400, 401, 404, 422, 500 status codes with meaningful messages
- Parametrized testing: testing multiple scenarios efficiently
- Database state verification: ensuring data persistence and integrity

**Transitions:**
With individual operations tested, we'll now build a complete test suite that covers our entire FastAPI application systematically.

**Key Principles:**
- CRUD operations should be tested in isolation and as complete workflows
- Error responses are as important as success responses for user experience
- Data validation testing prevents invalid data from reaching business logic
- Test data should represent realistic use cases and edge conditions

**Examples:**
- Complete user CRUD test suite with database verification
- Parametrized test covering various invalid input scenarios
- Testing cascade operations: deleting a user removes associated data

**Anti-patterns (woven in):**
- **Testing only expected outcomes**: Focusing only on successful CRUD operations ignores validation failures and error states that comprise significant user interaction.
- **Over-generating tests**: Creating separate test functions for every minor variation creates maintenance burden. Use parametrized testing for similar scenarios.

---

### 02.2 Building Your FastAPI Test Suite 💻

**Challenge Prompt:**
Create a comprehensive test suite for a FastAPI contacts API with endpoints for creating, reading, updating, and deleting contacts, including both success and error scenarios using pytest.

**Solution Code:**
```python
# test_contacts_api.py
import pytest
from fastapi.testclient import TestClient
from app import app, contacts_db  # Assuming in-memory storage

client = TestClient(app)

@pytest.fixture
def sample_contact():
    return {"name": "John Doe", "email": "john@example.com", "phone": "123-456-7890"}

def test_create_contact_success(sample_contact):
    response = client.post("/contacts", json=sample_contact)
    assert response.status_code == 201
    data = response.json()
    assert data["name"] == sample_contact["name"]
    assert "id" in data

def test_create_contact_invalid_email():
    invalid_contact = {"name": "Jane", "email": "invalid-email", "phone": "123-456-7890"}
    response = client.post("/contacts", json=invalid_contact)
    assert response.status_code == 422

def test_get_contact_exists():
    # Create contact first
    contact_data = {"name": "Test User", "email": "test@example.com", "phone": "111-222-3333"}
    create_response = client.post("/contacts", json=contact_data)
    contact_id = create_response.json()["id"]
    
    # Test retrieval
    response = client.get(f"/contacts/{contact_id}")
    assert response.status_code == 200
    assert response.json()["name"] == "Test User"

def test_get_contact_not_found():
    response = client.get("/contacts/999")
    assert response.status_code == 404

def test_update_contact_success():
    # Create and update workflow
    contact_data = {"name": "Update Test", "email": "update@example.com", "phone": "444-555-6666"}
    create_response = client.post("/contacts", json=contact_data)
    contact_id = create_response.json()["id"]
    
    updated_data = {"name": "Updated Name", "email": "updated@example.com", "phone": "777-888-9999"}
    response = client.put(f"/contacts/{contact_id}", json=updated_data)
    assert response.status_code == 200
    assert response.json()["name"] == "Updated Name"
```

**Challenge Code:**
```python
# test_contacts_api.py - Build comprehensive test suite
import pytest
from fastapi.testclient import TestClient
from app import app  # Import your FastAPI app

client = TestClient(app)

@pytest.fixture
def sample_contact():
    # Define sample contact data
    pass

def test_create_contact_success(sample_contact):
    # Test successful contact creation
    pass

def test_create_contact_invalid_email():
    # Test creation with invalid email format
    pass

def test_get_contact_exists():
    # Test retrieving existing contact
    pass

def test_get_contact_not_found():
    # Test retrieving non-existent contact
    pass

def test_update_contact_success():
    # Test successful contact update
    pass

def test_delete_contact_success():
    # Test successful contact deletion
    pass

# Add more test methods for edge cases
```

---

## Section 03: Test Planning and Strategy

### 03.0 Planning Unit Tests: Coverage, Edge Cases, and Test-Driven Development 📖

**Learning Objectives:**
- Design comprehensive test plans that identify critical test cases and edge conditions
- Apply Test-Driven Development (TDD) methodology to FastAPI development
- Understand test coverage metrics and their limitations
- Plan test scenarios that represent realistic user behavior and system boundaries

**Content Outline:**
- Test planning methodology: identifying what to test before writing code
- Edge case identification: boundary conditions, invalid inputs, resource limits
- TDD with FastAPI: Red-Green-Refactor cycle for API development
- Test coverage tools and interpretation: line coverage vs. branch coverage vs. meaningful coverage
- Representative test cases: normal operations, edge cases, and error conditions
- Test case prioritization: critical path testing vs. comprehensive coverage

**Transitions:**
With our planning strategy established, we'll implement a complete testing workflow that demonstrates these principles in practice.

**Key Principles:**
- Test planning prevents gaps in coverage and ensures critical scenarios are tested
- Edge cases often reveal the most important bugs in production systems
- TDD encourages better API design by considering usage patterns first
- Coverage metrics guide testing efforts but don't guarantee quality

**Examples:**
- Test plan for a user authentication API covering normal and edge cases
- TDD cycle: writing failing tests for new FastAPI endpoints before implementation
- Coverage report analysis showing high percentage but missing critical error paths

**Patterns (woven in):**
- **Test-Driven Development**: Write failing tests first, implement minimal code to pass, then refactor for quality. This ensures every line of code has a purpose and test coverage.
- **Edge case identification**: Systematically identify boundary conditions, invalid inputs, and resource limits that could break the system in unexpected ways.

**Best Practices (woven in):**
- **Error condition testing**: Always test how the system handles invalid inputs, missing resources, and unexpected states. Error scenarios are often more revealing than success scenarios.

**Anti-patterns (woven in):**
- **Testing only expected results**: Focusing solely on happy path scenarios ignores the error conditions and edge cases that users will inevitably encounter in production.

---

### 03.1 Comprehensive Testing Implementation 💻

**Challenge Prompt:**
Implement a complete TDD workflow for a FastAPI book library API, writing failing tests first for book CRUD operations, then implementing the endpoints to make tests pass, including comprehensive edge case coverage.

**Solution Code:**
```python
# test_books_tdd.py - TDD implementation
import pytest
from fastapi.testclient import TestClient
from app import app

client = TestClient(app)

class TestBookAPI:
    def test_create_book_success(self):
        book_data = {
            "title": "Test-Driven Development",
            "author": "Kent Beck",
            "isbn": "9780321146533",
            "pages": 240
        }
        response = client.post("/books", json=book_data)
        assert response.status_code == 201
        data = response.json()
        assert data["title"] == book_data["title"]
        assert "id" in data

    def test_create_book_missing_title(self):
        book_data = {"author": "Kent Beck", "isbn": "9780321146533"}
        response = client.post("/books", json=book_data)
        assert response.status_code == 422
        assert "title" in response.json()["detail"][0]["loc"]

    def test_create_book_invalid_isbn(self):
        book_data = {
            "title": "Test Book",
            "author": "Author",
            "isbn": "invalid-isbn",
            "pages": 200
        }
        response = client.post("/books", json=book_data)
        assert response.status_code == 422

    def test_get_books_empty_library(self):
        response = client.get("/books")
        assert response.status_code == 200
        assert response.json() == []

    def test_search_books_by_author(self):
        # Create test books
        book1 = {"title": "Book 1", "author": "Author A", "isbn": "1111111111111", "pages": 100}
        book2 = {"title": "Book 2", "author": "Author B", "isbn": "2222222222222", "pages": 200}
        
        client.post("/books", json=book1)
        client.post("/books", json=book2)
        
        response = client.get("/books?author=Author A")
        assert response.status_code == 200
        results = response.json()
        assert len(results) == 1
        assert results[0]["author"] == "Author A"

    def test_delete_nonexistent_book(self):
        response = client.delete("/books/999")
        assert response.status_code == 404
        assert "not found" in response.json()["detail"].lower()
```

**Challenge Code:**
```python
# test_books_tdd.py - Write failing tests first (TDD approach)
import pytest
from fastapi.testclient import TestClient
# from app import app  # Uncomment when app is created

# client = TestClient(app)  # Uncomment when app is ready

class TestBookAPI:
    def test_create_book_success(self):
        # Write test for successful book creation
        # This test should fail initially (Red phase)
        pass

    def test_create_book_missing_title(self):
        # Test validation error for missing title
        pass

    def test_create_book_invalid_isbn(self):
        # Test validation error for invalid ISBN format
        pass

    def test_get_books_empty_library(self):
        # Test getting books from empty library
        pass

    def test_search_books_by_author(self):
        # Test searching books by author
        pass

    def test_update_book_success(self):
        # Test successful book update
        pass

    def test_delete_nonexistent_book(self):
        # Test deleting book that doesn't exist
        pass

# Run tests with: pytest test_books_tdd.py -v
# All tests should fail initially (Red phase)
# Then implement app.py to make tests pass (Green phase)
# Finally refactor for better design (Refactor phase)
```

---

## Section 04: Assessment and Mastery

### 04.0 Testing Best Practices and Anti-Patterns 📖

**Learning Objectives:**
- Recognize and implement testing best practices that improve code quality and maintainability
- Identify common testing anti-patterns that reduce test effectiveness
- Understand the balance between test coverage and test quality
- Apply testing principles that scale with application growth

**Content Outline:**
- Testing best practices: clear test names, arrange-act-assert pattern, test independence
- Maintainable test code: DRY principles, shared fixtures, helper functions
- Test organization strategies: grouping related tests, logical test structure
- Performance considerations: fast tests vs. comprehensive tests
- Documentation through tests: tests as executable specifications
- Continuous integration: running tests automatically on code changes

**Transitions:**
Let's now assess your mastery of FastAPI testing concepts through practical scenarios that test your ability to apply these principles.

**Key Principles:**
- Good tests serve as documentation and specification for expected behavior
- Test maintenance cost should be proportional to the value they provide
- Fast feedback loops encourage frequent testing and better development practices
- Test quality matters more than test quantity for long-term project health

**Examples:**
- Refactoring a test suite to eliminate duplication while maintaining coverage
- Test naming conventions that clearly communicate intent and expected behavior
- CI/CD pipeline configuration for automated FastAPI testing

**Best Practices (woven in):**
- **Error condition testing**: Always verify how your FastAPI endpoints handle validation failures, missing resources, and unexpected inputs. These scenarios often reveal the most critical bugs.

**Anti-patterns (woven in):**
- **Over-generation of tests**: Creating separate test functions for every minor variation creates maintenance burden without adding value. Use parametrized tests for similar scenarios.
- **Testing only expected results**: Focusing solely on success cases while ignoring error conditions leaves significant gaps in your application's reliability.

---

### 04.1 FastAPI Testing Mastery Assessment 🧠

**Learning Objectives:**
- Demonstrate comprehensive understanding of FastAPI testing strategies
- Apply appropriate testing frameworks to different testing scenarios
- Identify optimal test planning approaches for API development
- Evaluate testing trade-offs and make informed decisions

**Question Format:** Multiple choice

**Evaluation Criteria:**
- Understanding of when to use unittest, pytest, or doctest
- Knowledge of FastAPI-specific testing patterns
- Ability to identify comprehensive test planning strategies
- Recognition of testing best practices and anti-patterns

**Score Interpretation:**
- 6-7 correct: Excellent mastery of FastAPI testing concepts
- 4-5 correct: Good understanding with minor gaps
- 2-3 correct: Basic knowledge, review recommended
- 0-1 correct: Foundational concepts need reinforcement

**Questions:**

1. When testing a FastAPI endpoint that depends on a database connection, what is the best approach to ensure test isolation?
   a) Use the production database with test data
   b) Create a separate test database and reset it after each test
   c) Use dependency injection to override the database dependency with a test fixture
   d) Mock all database calls at the HTTP level

2. Which testing framework is most appropriate for testing a FastAPI utility function that processes user input validation?
   a) unittest for its comprehensive assertion methods
   b) pytest for its simple syntax and fixtures
   c) doctest to provide executable documentation
   d) All frameworks are equally suitable

3. In a TDD approach with FastAPI, what should be your first step when adding a new API endpoint?
   a) Write the endpoint implementation
   b) Create the database schema
   c) Write a failing test that defines the expected behavior
   d) Set up the routing configuration

4. What is the most important aspect to test when validating FastAPI request/response cycles?
   a) Only the successful HTTP 200 responses
   b) Both success scenarios and error conditions (4xx, 5xx)
   c) Only the JSON response structure
   d) Only the request parsing logic

5. Which statement best describes comprehensive test planning for FastAPI applications?
   a) Write tests only for complex business logic functions
   b) Achieve 100% code coverage regardless of test quality
   c) Identify representative test cases including edge cases and error conditions
   d) Focus testing efforts only on the most frequently used endpoints

6. What is the primary advantage of using FastAPI's TestClient over standard HTTP testing libraries?
   a) TestClient is faster than other testing approaches
   b) TestClient automatically handles FastAPI's async/await patterns
   c) TestClient provides better error messages
   d) TestClient works only with pytest framework

7. When should you avoid creating a unit test for a FastAPI component?
   a) When the component is simple and unlikely to change
   b) When the component only handles error cases
   c) When creating a test would provide no meaningful validation of behavior
   d) When the component uses external dependencies

---

## Section 05: Outro

### 05.0 Your Testing Journey Forward

**Content Outline:**
- Course recap: You've mastered unittest, pytest, and doctest for FastAPI applications, learned to plan comprehensive test coverage, and implemented TDD workflows that ensure robust API development
- Connection to bigger picture: Testing is the foundation of reliable software systems - your FastAPI applications can now handle real-world usage with confidence through comprehensive test coverage
- Next steps and continued learning: Explore advanced testing topics like integration testing, performance testing, and testing in distributed systems; investigate testing tools like coverage.py for deeper metrics and hypothesis for property-based testing
- Resources for further exploration: FastAPI testing documentation, pytest plugin ecosystem, testing best practices from major Python projects, and testing communities for ongoing learning
- Encouragement and celebration: You now possess the skills to build FastAPI applications that are not just functional, but reliable, maintainable, and ready for production use

**Note:** This is conclusion only - no theory, exercises, or assessment.

---