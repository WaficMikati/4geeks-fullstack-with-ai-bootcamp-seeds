# Course Outline: Debugging

**Title:** Debugging: Evidence Over Assumption
**Learnpack:** + Debugging
**Prerequisite:** Week 6 Day 17 - Interacting with APIs (students already familiar with Network tab basics, HTTP methods, and status codes)
**Target Audience:** Beginner frontend developers learning React/Next.js who need systematic approaches to finding and fixing bugs
**Total Lessons:** 18
**Estimated Total Length:** ~9,500 words
**Format:** Mixed (33% hands-on)

---

## Course Description

Every developer spends significant time debugging. The difference between a frustrated developer and an effective one isn't the absence of bugs—it's the ability to find and fix them systematically. This course transforms debugging from a random guessing game into a methodical process.

You'll master the browser's Developer Tools, learning to use each panel for its intended purpose: Elements for layout issues, Console for JavaScript errors, Network for API problems, and React DevTools for component state. More importantly, you'll develop the mindset of "evidence over assumption"—the habit of gathering data before making changes.

By the end of this course, you'll approach bugs with confidence, knowing exactly which tool to reach for and how to interpret what it tells you.

---

## Course Philosophy

This course emphasizes:
- **Evidence over assumption**: Always gather data before making changes
- **Right tool for the right problem**: Each DevTools panel serves a specific purpose
- **Systematic investigation**: Follow a repeatable process, not random guessing
- **Clean debugging habits**: Debug effectively without cluttering your codebase

---

## Course Statistics Summary

| Section | Lessons | Estimated Words |
|---------|---------|-----------------|
| 00 - Welcome | 1 | ~450 |
| 01 - The Debugging Mindset | 3 | ~1,500 |
| 02 - The Elements Panel | 3 | ~1,600 |
| 03 - The Console Panel | 3 | ~1,600 |
| 04 - The Network Panel | 3 | ~1,600 |
| 05 - React Developer Tools | 2 | ~1,100 |
| 06 - Assessment | 2 | ~1,200 |
| 07 - Conclusion | 1 | ~450 |
| **Total** | **18** | **~9,500** |

---

## Section 00: Welcome

### 00.0 Why Debugging Matters 📖 (~450 words)

**Learning Objectives:**
- Recognize that debugging is a core developer skill, not a sign of failure
- Understand the "evidence over assumption" principle that guides effective debugging
- Identify the four main DevTools panels covered in this course

**Content Outline:**
- The reality: Professional developers spend 30-50% of their time debugging
- Why bugs aren't failures—they're feedback about your understanding
- The costly mistake: Making random changes without evidence
- Introduction to the "evidence over assumption" mindset
- Overview of the four investigation tools: Elements, Console, Network, React DevTools
- How this course builds on your existing knowledge of APIs and the Network tab

**Transitions:**
This lesson sets the philosophical foundation. Next, we'll explore how to categorize bugs so you know which tool to reach for.

**Key Principles:**
- Debugging is investigation, not guessing
- The right tool depends on the type of problem
- Evidence first, changes second

**Examples:**
- A developer who spends 2 hours changing CSS randomly vs. one who opens Elements and finds the issue in 2 minutes
- The frustration of "it worked yesterday" without any data about what changed

---

## Section 01: The Debugging Mindset

### 01.0 Evidence Over Assumption 📖 (~500 words)

**Learning Objectives:**
- Apply the "evidence over assumption" principle to debugging scenarios
- Distinguish between productive debugging and random trial-and-error
- Formulate hypotheses before making code changes

**Content Outline:**
- The trap: Changing code based on what you *think* is wrong
- The scientific method applied to debugging: Observe → Hypothesize → Test → Conclude
- What counts as evidence: Error messages, console output, network responses, visual inspection
- The cost of skipping evidence: Wasted time, new bugs introduced, frustration
- How to formulate a testable hypothesis: "If X is the problem, then I should see Y in the DevTools"

**Transitions:**
Now that you understand the importance of evidence, let's categorize the types of errors you'll encounter so you know where to look.

**Key Principles:**
- Never change code without first understanding what's happening
- A hypothesis without evidence is just a guess
- The DevTools are your evidence-gathering instruments

**Examples:**
- Bad approach: "The button doesn't work, let me rewrite the onClick handler"
- Good approach: "The button doesn't work. Let me check Console for errors, then inspect the element to verify the handler is attached"

---

### 01.1 Types of Frontend Errors 📖 (~500 words)

**Learning Objectives:**
- Classify frontend bugs into four categories: Layout, JavaScript, Network, and State
- Match each bug category to its primary DevTools panel
- Recognize symptoms that indicate each bug type

**Content Outline:**
- **Layout bugs**: Things look wrong (position, size, visibility, spacing)
  - Primary tool: Elements panel
  - Symptoms: Overlapping elements, broken responsive design, missing content
- **JavaScript bugs**: Code doesn't execute correctly
  - Primary tool: Console panel
  - Symptoms: Features don't work, error messages, unexpected behavior
- **Network bugs**: Data doesn't arrive or arrives incorrectly
  - Primary tool: Network panel
  - Symptoms: Loading forever, missing data, wrong data displayed
- **State bugs**: React components behave unexpectedly
  - Primary tool: React DevTools
  - Symptoms: UI doesn't update, stale data, props not passing correctly
- Why bugs often span multiple categories

**Transitions:**
You can now categorize bugs. Next, you'll practice identifying which category a bug belongs to.

**Key Principles:**
- Correct diagnosis precedes effective treatment
- Start with the most likely category based on symptoms
- Be prepared to pivot if your first hypothesis is wrong

**Examples:**
- "The user list is empty" could be: Network (API failed), State (data not stored correctly), or Layout (CSS hiding the list)
- "The modal won't close" is likely JavaScript (event handler issue) or State (modal state not updating)

---

### 01.2 Identifying Your Bug Category 💻 (~400 words)

**Challenge Prompt:**
For each bug description, identify the category (Layout, JavaScript, Network, or State) and which DevTools panel to open first.

**Solution Code:**
```javascript
const bugAnalysis = [
  {
    bug: "Button appears but nothing happens when clicked",
    category: "JavaScript",
    panel: "Console"
  },
  {
    bug: "Sidebar overlaps main content on resize",
    category: "Layout",
    panel: "Elements"
  },
  {
    bug: "Username shows 'undefined' after login",
    category: "State",
    panel: "React DevTools"
  },
  {
    bug: "Page shows spinner forever",
    category: "Network",
    panel: "Network"
  }
];
```

**Challenge Code:**
```javascript
const bugAnalysis = [
  {
    bug: "Button appears but nothing happens when clicked",
    category: "", // "Layout", "JavaScript", "Network", or "State"
    panel: ""     // "Elements", "Console", "Network", or "React DevTools"
  },
  {
    bug: "Sidebar overlaps main content on resize",
    category: "",
    panel: ""
  },
  {
    bug: "Username shows 'undefined' after login",
    category: "",
    panel: ""
  },
  {
    bug: "Page shows spinner forever",
    category: "",
    panel: ""
  }
];
```

---

## Section 02: The Elements Panel

### 02.0 Inspecting and Modifying the DOM 📖 (~550 words)

**Learning Objectives:**
- Navigate the Elements panel to locate specific DOM nodes
- Use the element selector tool to jump directly to elements on the page
- Understand the relationship between the DOM tree and the rendered page

**Content Outline:**
- Opening DevTools and accessing the Elements panel (F12, Cmd/Ctrl+Shift+I)
- The element selector tool: Click the icon (or Cmd/Ctrl+Shift+C) then click any element
- Reading the DOM tree: Parent-child relationships, nesting, attributes
- Hovering over elements to see their boundaries highlighted
- The Styles pane: Where CSS rules come from and how they're applied
- The Computed pane: The final calculated values after all CSS is resolved
- Live editing: Double-click to modify attributes, text content, or HTML structure
- Why changes here are temporary (refresh resets everything)

**Transitions:**
You can now navigate the DOM. Next, we'll focus on live CSS prototyping.

**Key Principles:**
- The Elements panel shows the current state of the DOM, not your source code
- Use the selector tool to avoid hunting through the tree manually
- Changes are temporary—use them to experiment before modifying your actual code

**Examples:**
- Finding why a button is hidden: Select it, check `display`, `visibility`, `opacity` in Computed
- Discovering an unexpected parent: Element isn't where you thought because of React portals

---

### 02.1 Live CSS Prototyping 📖 (~500 words)

**Learning Objectives:**
- Modify CSS properties directly in the browser to test fixes instantly
- Use the browser as a safe experimentation environment before changing code
- Copy tested CSS changes back to your source files

**Content Outline:**
- The anti-pattern: Editing CSS in your code, saving, waiting for reload, checking, repeating
- The pattern: Edit directly in Elements, see instant results, copy working solution to code
- Adding new properties: Click in the Styles pane, type property name, press Tab, type value
- Toggling properties: Checkbox next to each rule enables/disables it instantly
- Adding new CSS rules: Click the + icon to create a new selector
- The box model visualization: See margin, border, padding, content as a diagram
- Forcing element states: Right-click element → Force state → :hover, :focus, :active
- Workflow: Experiment → Find solution → Copy to your CSS file → Verify

**Transitions:**
You've learned to prototype CSS. Now let's apply this skill to fix a real layout bug.

**Key Principles:**
- The browser is your CSS sandbox—experiment freely
- Always copy your solution to source code before refreshing
- Force states to debug hover/focus styles without triggering them manually

**Examples:**
- Testing responsive fixes: Modify width values and see layout shift instantly
- Debugging z-index: Toggle visibility of overlapping elements to understand stacking

---

### 02.2 Fix a Broken Layout 💻 (~400 words)

**Challenge Prompt:**
The card component has layout issues: content overflows and the image isn't responsive. Identify the CSS problems and provide fixes.

**Solution Code:**
```css
/* Fixed styles */
.card {
  width: 300px;
  overflow: hidden; /* FIX: Prevents content overflow */
}

.card-image {
  width: 100%;      /* FIX: Was 400px, now responsive */
  height: 200px;
  object-fit: cover; /* FIX: Maintains aspect ratio */
}

.card-title {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap; /* FIX: Handles long titles */
}
```

**Challenge Code:**
```css
/* Broken styles - fix the issues */
.card {
  width: 300px;
  /* What's missing to contain overflow? */
}

.card-image {
  width: 400px; /* This seems wrong... */
  height: 200px;
}

.card-title {
  /* What if the title is very long? */
}

/* Document what you found in Elements panel:
   1.
   2.
   3.
*/
```

---

## Section 03: The Console Panel

### 03.0 Beyond console.log 📖 (~550 words)

**Learning Objectives:**
- Use console methods beyond basic log (warn, error, table, group, time)
- Read and interpret error stack traces to locate the source of bugs
- Filter console output to focus on relevant messages

**Content Outline:**
- The anti-pattern: `console.log("here")`, `console.log("here 2")`, `console.log("wtf")`
- **console.log with labels**: Always include context: `console.log("User data:", userData)`
- **console.warn**: For non-critical issues that should be addressed
- **console.error**: For errors that need attention (appears in red)
- **console.table**: Displays arrays and objects in a readable table format
- **console.group / console.groupEnd**: Organize related logs into collapsible sections
- **console.time / console.timeEnd**: Measure how long operations take
- Reading stack traces: The error message, file names, line numbers, the call sequence
- Filtering console output: The dropdown to show only Errors, Warnings, or Info
- Preserving logs: Enable "Preserve log" to keep messages across page navigation

**Transitions:**
Better logging is a start, but the real power comes from breakpoints—pausing execution to inspect values at any moment.

**Key Principles:**
- Labeled logs are infinitely more useful than anonymous ones
- Use the right console method for the right purpose
- Stack traces tell you the path of execution that led to the error

**Examples:**
- `console.table(users)` instantly shows an array of user objects in readable format
- `console.time("API call"); await fetch(...); console.timeEnd("API call");` measures request duration

---

### 03.1 Using Breakpoints and the Debugger 📖 (~500 words)

**Learning Objectives:**
- Set breakpoints in the Sources panel to pause code execution
- Inspect variable values at any point during execution
- Step through code line by line to understand the flow

**Content Outline:**
- Why breakpoints beat console.log: See ALL variables at once, not just what you logged
- Opening the Sources panel and finding your files
- Setting a breakpoint: Click the line number (blue marker appears)
- Triggering the breakpoint: Interact with your app to run that code
- The paused state: Execution stops, you can inspect everything
- The Scope pane: Local variables, closure variables, global variables
- Stepping controls:
  - Step over (F10): Execute current line, move to next
  - Step into (F11): Enter the function being called
  - Step out (Shift+F11): Finish current function, return to caller
  - Resume (F8): Continue until next breakpoint
- Conditional breakpoints: Right-click → Add conditional breakpoint
- The `debugger` statement: Write `debugger;` in your code to create a programmatic breakpoint

**Transitions:**
You now have powerful tools for JavaScript debugging. Let's apply them to fix a real failing function.

**Key Principles:**
- Breakpoints let you freeze time and examine the entire program state
- Step through code when you don't understand why something is happening
- Conditional breakpoints save you from pausing on every loop iteration

**Examples:**
- Conditional breakpoint: `user.id === 5` only pauses when debugging a specific user
- Watch expression: `items.length` shows you how many items exist at each step

---

### 03.2 Debug a Failing Function 💻 (~400 words)

**Challenge Prompt:**
The `calculateTotal` function returns wrong values. Use breakpoints to find the bugs.

**Solution Code:**
```javascript
const calculateTotal = (items, discountCode) => {
  let subtotal = 0;
  for (const item of items) {
    subtotal += item.price * item.quantity; // FIX: Was missing * quantity
  }
  
  let discount = 0;
  if (discountCode) {
    const discounts = { 'SAVE10': 0.10, 'SAVE20': 0.20 };
    const rate = discounts[discountCode.toUpperCase()]; // FIX: Case mismatch
    if (rate) discount = subtotal * rate;
  }
  
  return subtotal - discount; // FIX: Was returning subtotal only
};
```

**Challenge Code:**
```javascript
const calculateTotal = (items, discountCode) => {
  let subtotal = 0;
  for (const item of items) {
    subtotal += item.price; // Something missing?
  }
  
  let discount = 0;
  if (discountCode) {
    const discounts = { 'SAVE10': 0.10, 'SAVE20': 0.20 };
    const rate = discounts[discountCode.toLowerCase()]; // Check this
    if (rate) discount = subtotal * rate;
  }
  
  return subtotal; // Is this right?
};

// Test: calculateTotal([{price: 10, quantity: 2}], 'SAVE10')
// Expected: 18, Actual: ?
```

---

## Section 04: The Network Panel

### 04.0 Request Autopsy: Diagnosing API Issues 📖 (~550 words)

**Learning Objectives:**
- Filter network requests to focus on API calls (Fetch/XHR)
- Analyze failed requests by examining status codes, headers, and response bodies
- Distinguish between client-side and server-side errors

**Content Outline:**
- Building on Day 17: You know HTTP methods and status codes, now we diagnose failures
- Opening the Network panel and filtering by Fetch/XHR
- The request list: Each row is one request, color-coded by status
  - Green/gray: Success (2xx, 3xx)
  - Red: Error (4xx, 5xx)
- Selecting a request to see details:
  - **Headers tab**: Request URL, method, status code, request/response headers
  - **Payload tab**: What you sent (request body, query parameters)
  - **Response tab**: What the server returned
  - **Timing tab**: How long each phase took
- The "Request Autopsy" pattern:
  1. Find the failing request (look for red)
  2. Check the status code (4xx = your fault, 5xx = server's fault)
  3. Read the response body (often contains error details)
  4. Compare Payload to what you intended to send
  5. Check headers (missing Authorization? Wrong Content-Type?)

**Transitions:**
You can now diagnose API failures. Next, we'll simulate real-world network conditions.

**Key Principles:**
- The Network panel shows the truth about what was sent and received
- 4xx errors mean check your request; 5xx errors mean contact the backend team
- The response body often contains the real error message

**Examples:**
- User reports "login doesn't work": Find the login request, see 401, check if token was included
- Data not loading: Find the request, see it's still "pending" → server never responded

---

### 04.1 Simulating Real-World Conditions 📖 (~500 words)

**Learning Objectives:**
- Use network throttling to simulate slow connections
- Test how your application behaves under degraded conditions
- Identify race conditions and timing-dependent bugs

**Content Outline:**
- The "works on my machine" anti-pattern: Fast WiFi hides real-world problems
- Opening throttling: Network panel → "No throttling" dropdown
- Preset options: Fast 3G, Slow 3G, Offline
- Custom profiles: Create your own speed/latency combinations
- What throttling reveals:
  - Loading states: Does your UI show a spinner or skeleton?
  - Race conditions: Do requests return in the wrong order?
  - Timeouts: Does your app handle requests that take too long?
  - Error states: What happens when requests fail?
- Testing offline behavior:
  - Set to Offline
  - Try to perform actions
  - Does the app show helpful error messages?
- The CPU slowdown option (Performance panel): Simulates slower devices

**Transitions:**
You understand how to simulate conditions. Now let's practice finding a failing request.

**Key Principles:**
- Test on the conditions your users actually have
- Loading states are features, not afterthoughts
- The fastest code means nothing if the network is slow

**Examples:**
- Fast 3G testing reveals your image gallery takes 15 seconds to become interactive
- Slow 3G shows that your app makes 47 API calls on page load

---

### 04.2 Find the Failing Request 💻 (~400 words)

**Challenge Prompt:**
"Load Comments" shows a spinner then nothing appears. Use the Network panel to diagnose why.

**Solution Code:**
```javascript
const loadComments = async (postId) => {
  const response = await fetch(`/api/posts/${postId}/comments`, { // FIX: Added /api prefix
    headers: {
      'Authorization': `Bearer ${localStorage.getItem('token')}`, // FIX: Was missing
      'Content-Type': 'application/json'
    }
  });
  
  if (!response.ok) { // FIX: Was not checking response status
    throw new Error(`HTTP ${response.status}`);
  }
  
  return response.json();
};
```

**Challenge Code:**
```javascript
const loadComments = async (postId) => {
  const response = await fetch(`/posts/${postId}/comments`); // Check URL
  return response.json(); // Is this enough?
};

/* Network Panel Diagnosis:
   1. What status code did you see?
   2. What was in the Response tab?
   3. What headers were missing?
*/
```

---

## Section 05: React Developer Tools

### 05.0 Inspecting Component State and Props 📖 (~550 words)

**Learning Objectives:**
- Install and navigate React Developer Tools browser extension
- Inspect component props and state in real-time
- Identify components with unexpected state values

**Content Outline:**
- Installing React DevTools: Chrome Web Store or Firefox Add-ons
- Two new tabs appear: Components and Profiler (we focus on Components)
- The Components tab: Shows your React component tree (not the DOM)
- Selecting components: Click in the tree or use the selector tool
- The right panel shows:
  - **Props**: Values passed from parent
  - **Hooks**: useState, useEffect, and custom hook values
  - **Source**: Link to the component in Sources panel
- Editing state live: Double-click a state value to change it
- Searching: Use the search box to find components by name
- Highlighting updates: Settings → Highlight updates → See which components re-render
- The difference from Elements panel:
  - Elements shows DOM nodes (divs, spans)
  - React DevTools shows React components (UserCard, Header)

**Transitions:**
You can now inspect React components. Let's apply this to debug a component with state issues.

**Key Principles:**
- React DevTools shows the React perspective, not the DOM perspective
- State and props inspection helps when data exists but displays wrong
- You can modify state live to test hypotheses

**Examples:**
- User profile shows wrong name: Select UserProfile component, check if `user` prop has correct data
- Counter doesn't update: Check if useState value changes when you click

---

### 05.1 Debug a React Component 💻 (~400 words)

**Challenge Prompt:**
The ShoppingCart shows wrong item count and total. Use React DevTools to find the bugs.

**Solution Code:**
```jsx
const ShoppingCart = ({ items }) => {
  // FIX: Was using items.length instead of summing quantities
  const itemCount = items.reduce((sum, item) => sum + item.quantity, 0);
  
  // FIX: Was not multiplying price * quantity
  const total = items.reduce((sum, item) => sum + (item.price * item.quantity), 0);

  return (
    <div>
      <h2>Cart ({itemCount} items)</h2>
      <p>Total: ${total.toFixed(2)}</p>
    </div>
  );
};
```

**Challenge Code:**
```jsx
const ShoppingCart = ({ items }) => {
  const itemCount = items.length; // Check this
  const total = items.reduce((sum, item) => sum + item.price, 0); // And this

  return (
    <div>
      <h2>Cart ({itemCount} items)</h2>
      <p>Total: ${total.toFixed(2)}</p>
    </div>
  );
};

// Test: items = [{price: 25, quantity: 2}, {price: 10, quantity: 3}]
// Expected: 5 items, $80.00
```

---

## Section 06: Assessment

### 06.0 Debugging Anti-Patterns 📖 (~500 words)

**Learning Objectives:**
- Recognize common debugging anti-patterns that waste time
- Identify the correct approach to replace each anti-pattern
- Apply the "evidence over assumption" principle to avoid these traps

**Content Outline:**
- **Console Driven Development**
  - Anti-pattern: `console.log("here")`, `console.log("here2")` scattered everywhere
  - Problem: No labels, no context, clutter obscures the real issue
  - Solution: Use labeled logs, breakpoints, or structured console methods
- **Blind CSS Changes**
  - Anti-pattern: Change in editor → save → reload → check → repeat
  - Problem: Slow iteration, easy to lose track of what you tried
  - Solution: Prototype in Elements panel, copy working solution to code
- **"It Doesn't Work" Without Evidence**
  - Anti-pattern: Declaring failure without opening DevTools
  - Problem: No hypothesis, no data, no direction
  - Solution: Open the relevant panel first, gather evidence, then diagnose
- **"Works on My Machine" Testing**
  - Anti-pattern: Only testing on your development setup
  - Problem: Fast networks and powerful CPUs hide real-world issues
  - Solution: Use throttling and CPU slowdown to simulate real conditions
- **Random Changes Until It Works**
  - Anti-pattern: Changing code without understanding the bug
  - Problem: May fix symptom but not cause, may introduce new bugs
  - Solution: Understand before changing; form a hypothesis and test it

**Transitions:**
You've learned to recognize what NOT to do. Now let's verify your understanding.

**Key Principles:**
- Every anti-pattern has a productive alternative
- Time spent gathering evidence saves time overall
- Professional debugging is systematic, not random

**Examples:**
- Instead of 20 unlabeled console.logs, set one breakpoint and inspect all variables
- Instead of editing CSS in code repeatedly, spend 2 minutes in Elements panel

---

### 06.1 Knowledge Check 🧠 (~700 words)

**Learning Objectives:**
- Demonstrate understanding of when to use each DevTools panel
- Apply the "evidence over assumption" principle to debugging scenarios
- Identify the correct debugging approach for common bug types

**Question Format:** Multiple choice (7 questions)

**Evaluation Criteria:**
- 6-7 correct: Excellent understanding of debugging practices
- 4-5 correct: Good foundation, review the missed concepts
- Below 4: Revisit the relevant sections before proceeding

---

**Question 1:** A button "doesn't do anything" when clicked. What should you do FIRST?

A) Rewrite the onClick handler  
B) Check the Console panel for JavaScript errors  
C) Ask the user for more details  
D) Add console.log statements  

**Correct Answer:** B

**Explanation:** The first step is gathering evidence. The Console panel will immediately show if there's a JavaScript error when the button is clicked.

---

**Question 2:** You're debugging a layout issue where elements overlap. Which panel should you open first?

A) Console  
B) Network  
C) Elements  
D) React DevTools  

**Correct Answer:** C

**Explanation:** Layout issues are CSS/DOM problems. The Elements panel lets you inspect computed styles and the box model.

---

**Question 3:** You want to test a CSS change without modifying your source code. What is the correct approach?

A) Use the Console to modify styles with JavaScript  
B) Edit the styles directly in the Elements panel  
C) Create a temporary CSS file  
D) Use the Network panel  

**Correct Answer:** B

**Explanation:** The Elements panel lets you modify CSS in real-time. Changes are temporary, making it perfect for experimenting.

---

**Question 4:** Your API call returns a 401 error. What does this indicate?

A) The server crashed  
B) The resource doesn't exist  
C) Your authentication credentials are invalid or missing  
D) You sent malformed data  

**Correct Answer:** C

**Explanation:** 401 (Unauthorized) indicates an authentication problem. Check the request headers for the Authorization header.

---

**Question 5:** You suspect a race condition where API responses arrive in the wrong order. Which tool would be MOST helpful?

A) React DevTools  
B) Network panel with throttling enabled  
C) Console panel with console.time  
D) Elements panel  

**Correct Answer:** B

**Explanation:** Network throttling slows down requests, making race conditions more visible and reproducible.

---

**Question 6:** What is the main advantage of breakpoints over console.log?

A) Breakpoints are faster to set up  
B) Breakpoints show all variables in scope, not just logged ones  
C) Breakpoints work in production  
D) Breakpoints automatically fix bugs  

**Correct Answer:** B

**Explanation:** When execution pauses at a breakpoint, you can inspect ALL variables in the current scope.

---

**Question 7:** A React component displays "undefined" for the user's name. The API returns correct data. Which tool should you use?

A) Network panel  
B) Console panel  
C) React DevTools  
D) Elements panel  

**Correct Answer:** C

**Explanation:** Since API data is correct, the bug is in how data flows through React components. React DevTools lets you inspect props and state at each level.

---

**Score Interpretation:**
- **6-7 correct:** You've mastered the debugging fundamentals.
- **4-5 correct:** Good understanding. Review missed questions.
- **Below 4:** Revisit the sections covering unfamiliar tools.

---

## Section 07: Conclusion

### 07.0 Your Debugging Toolkit (~450 words)

**Content Outline:**

**Course Recap: What You've Accomplished**

You started this course understanding that debugging is inevitable but perhaps feeling like it was a frustrating guessing game. Now you have a systematic approach: categorize the bug, open the right tool, gather evidence, form a hypothesis, and verify before changing code.

You've mastered the four essential DevTools panels:
- **Elements** for layout and CSS issues—prototype fixes live before touching your code
- **Console** for JavaScript errors—use breakpoints instead of scattered console.logs
- **Network** for API problems—perform a "request autopsy" on every failing call
- **React DevTools** for component state—trace data flow through your React tree

**Connection to the Bigger Picture**

Debugging skills compound over time. Every bug you solve systematically builds your pattern recognition. You'll start seeing familiar symptoms and reaching for the right tool instinctively. The developers who spend hours frustrated are usually the ones skipping the evidence-gathering step. You now know better.

These skills also make you a better collaborator. When you report a bug to a teammate, you'll provide specific details: "The POST to /api/orders returns 422 with validation error 'quantity must be positive'" instead of "the checkout doesn't work."

**Next Steps and Continued Learning**

The next lesson in this skill covers **performance optimization**—measuring and improving your frontend's Core Web Vitals. Debugging and performance are closely related: the same DevTools you've learned have Performance and Lighthouse tabs that reveal exactly what's slowing down your app.

**Resources for Further Exploration**
- Chrome DevTools documentation: Comprehensive guides for every panel
- Firefox Developer Tools: Alternative browser with slightly different features
- React DevTools GitHub: Latest features and debugging techniques
- "Debugging" category on web.dev: Google's practical debugging guides

**Final Encouragement**

Every expert developer you admire has stared at confusing bugs for hours. The difference is they've built the habit of reaching for evidence instead of making assumptions. You now have that habit too.

The next time something breaks, you won't panic. You'll open DevTools, categorize the bug, and start gathering data. That calm, methodical approach is what separates professional developers from everyone else.

You've got this. Now go find some bugs.

---