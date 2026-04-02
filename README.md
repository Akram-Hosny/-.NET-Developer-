<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>.NET Developer Interview Preparation Guide</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Fira+Code&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.7;
            color: #1a1a2e;
            background: #ffffff;
            font-size: 15px;
        }
        
        /* Cover Page */
        .cover-page {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
            padding: 60px 20px;
            page-break-after: always;
        }
        
        .cover-page h1 {
            font-size: 3.5em;
            font-weight: 800;
            margin-bottom: 20px;
            letter-spacing: -1px;
        }
        
        .cover-page .subtitle {
            font-size: 1.4em;
            font-weight: 300;
            opacity: 0.95;
            margin-bottom: 40px;
        }
        
        .cover-page .meta {
            font-size: 1em;
            opacity: 0.85;
            line-height: 2;
        }
        
        .cover-page .badge {
            display: inline-block;
            background: rgba(255,255,255,0.2);
            padding: 10px 25px;
            border-radius: 50px;
            margin: 10px;
            backdrop-filter: blur(10px);
        }
        
        /* Table of Contents */
        .toc {
            background: #f8f9fa;
            padding: 60px 40px;
            page-break-after: always;
        }
        
        .toc h2 {
            font-size: 2em;
            color: #667eea;
            margin-bottom: 30px;
            text-align: center;
        }
        
        .toc-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 15px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .toc-item {
            background: white;
            padding: 18px 22px;
            border-radius: 12px;
            border-left: 4px solid #667eea;
            box-shadow: 0 2px 8px rgba(0,0,0,0.06);
            transition: transform 0.2s;
        }
        
        .toc-item:hover {
            transform: translateX(5px);
        }
        
        .toc-item .num {
            font-weight: 700;
            color: #667eea;
            margin-right: 10px;
        }
        
        .toc-item a {
            color: #333;
            text-decoration: none;
            font-weight: 500;
        }
        
        /* Main Content Container */
        .container {
            max-width: 960px;
            margin: 0 auto;
            padding: 40px 30px;
        }
        
        /* Section Headers */
        .section-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 35px 40px;
            border-radius: 16px;
            margin: 60px 0 30px 0;
            page-break-after: avoid;
        }
        
        .section-header h2 {
            font-size: 2em;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .section-header p {
            opacity: 0.9;
            font-size: 1.05em;
        }
        
        /* Topic Headers */
        h3 {
            font-size: 1.6em;
            color: #2d3748;
            margin: 45px 0 20px 0;
            padding-bottom: 12px;
            border-bottom: 3px solid #667eea;
            display: inline-block;
            page-break-after: avoid;
        }
        
        h4 {
            font-size: 1.25em;
            color: #4a5568;
            margin: 28px 0 15px 0;
            page-break-after: avoid;
        }
        
        /* Definition Box */
        .definition-box {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            border-left: 5px solid #667eea;
            padding: 22px 28px;
            border-radius: 10px;
            margin: 20px 0;
            page-break-inside: avoid;
        }
        
        .definition-box strong {
            color: #667eea;
            font-size: 1.1em;
        }
        
        /* Code Blocks */
        pre {
            background: #1e1e3f;
            color: #a9b1d6;
            padding: 24px;
            border-radius: 12px;
            overflow-x: auto;
            font-family: 'Fira Code', 'Consolas', monospace;
            font-size: 13.5px;
            line-height: 1.6;
            margin: 20px 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
            page-break-inside: avoid;
        }
        
        pre code {
            background: none;
            padding: 0;
            color: inherit;
        }
        
        code {
            background: #edf2f7;
            color: #d53f8c;
            padding: 3px 8px;
            border-radius: 5px;
            font-family: 'Fira Code', monospace;
            font-size: 0.9em;
        }
        
        pre code {
            background: transparent;
            color: inherit;
            padding: 0;
        }
        
        /* Tables */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 25px 0;
            font-size: 14px;
            box-shadow: 0 2px 15px rgba(0,0,0,0.08);
            border-radius: 10px;
            overflow: hidden;
            page-break-inside: avoid;
        }
        
        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px 18px;
            text-align: left;
            font-weight: 600;
            font-size: 0.92em;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        td {
            padding: 14px 18px;
            border-bottom: 1px solid #e2e8f0;
            vertical-align: top;
        }
        
        tr:last-child td {
            border-bottom: none;
        }
        
        tr:nth-child(even) {
            background: #f7fafc;
        }
        
        tr:hover {
            background: #edf2f7;
        }
        
        /* Info Boxes */
        .info-box {
            background: #ebf8ff;
            border-left: 5px solid #4299e1;
            padding: 20px 25px;
            border-radius: 10px;
            margin: 20px 0;
            page-break-inside: avoid;
        }
        
        .warning-box {
            background: #fffaf0;
            border-left: 5px solid #ed8936;
            padding: 20px 25px;
            border-radius: 10px;
            margin: 20px 0;
            page-break-inside: avoid;
        }
        
        .success-box {
            background: #f0fff4;
            border-left: 5px solid #48bb78;
            padding: 20px 25px;
            border-radius: 10px;
            margin: 20px 0;
            page-break-inside: avoid;
        }
        
        .box-title {
            font-weight: 700;
            font-size: 1.05em;
            margin-bottom: 8px;
            display: block;
        }
        
        /* Lists */
        ul, ol {
            margin: 15px 0 15px 25px;
        }
        
        li {
            margin: 8px 0;
            line-height: 1.65;
        }
        
        li::marker {
            color: #667eea;
            font-weight: bold;
        }
        
        /* Diagram Box */
        .diagram-box {
            background: #fafafa;
            border: 2px dashed #cbd5e0;
            padding: 25px;
            border-radius: 12px;
            margin: 25px 0;
            font-family: 'Fira Code', monospace;
            font-size: 13px;
            line-height: 1.55;
            overflow-x: auto;
            white-space: pre;
            page-break-inside: avoid;
        }
        
        /* Key Points Grid */
        .key-points {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin: 25px 0;
        }
        
        .key-point {
            background: #f7fafc;
            padding: 18px;
            border-radius: 10px;
            border-top: 3px solid #667eea;
        }
        
        .key-point strong {
            color: #667eea;
            display: block;
            margin-bottom: 5px;
        }
        
        /* Page Break Utilities */
        .page-break {
            page-break-before: always;
        }
        
        .no-break {
            page-break-inside: avoid;
        }
        
        /* Print Styles */
        @media print {
            body {
                -webkit-print-color-adjust: exact !important;
                print-color-adjust: exact !important;
            }
            
            .cover-page {
                min-height: 100vh;
                page-break-after: always;
            }
            
            .section-header {
                background: #667eea !important;
                -webkit-print-color-adjust: exact !important;
            }
            
            pre {
                background: #1e1e3f !important;
                -webkit-print-color-adjust: exact !important;
            }
            
            table th {
                background: #667eea !important;
                -webkit-print-color-adjust: exact !important;
            }
            
            .page-break {
                page-break-before: always;
            }
        }
        
        /* Comparison Section */
        .comparison {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin: 25px 0;
        }
        
        .compare-col {
            background: #f7fafc;
            padding: 20px;
            border-radius: 12px;
            border-top: 4px solid #667eea;
        }
        
        .compare-col.bad {
            border-top-color: #fc8181;
        }
        
        .compare-col.good {
            border-top-color: #68d391;
        }
        
        .compare-col h5 {
            font-size: 1.1em;
            margin-bottom: 12px;
            color: #2d3748;
        }
        
        @media (max-width: 768px) {
            .comparison {
                grid-template-columns: 1fr;
            }
            
            .cover-page h1 {
                font-size: 2.2em;
            }
            
            .container {
                padding: 20px 15px;
            }
        }

        /* Cheat Sheet Table Special Style */
        .cheat-sheet-table {
            font-size: 13.5px;
        }
        
        .cheat-sheet-table th:first-child {
            width: 8%;
        }
        
        .cheat-sheet-table th:nth-child(2) {
            width: 32%;
        }
        
        .cheat-sheet-table td:last-child {
            font-size: 12.8px;
            line-height: 1.5;
        }
    </style>
</head>
<body>

<!-- ==================== COVER PAGE ==================== -->
<div class="cover-page">
    <h1>📚 .NET Developer</h1>
    <div class="subtitle">Complete Interview Preparation Guide</div>
    <div style="margin: 30px 0;">
        <span class="badge">🔷 C# & OOP</span>
        <span class="badge">🗄️ Entity Framework</span>
        <span class="badge">🌐 ASP.NET Core</span>
        <span class="badge">🚀 Advanced Topics</span>
    </div>
    <div class="meta">
        <p><strong>Beginner-Friendly</strong> • Comprehensive Examples • Practical Code</p>
        <p style="margin-top: 15px; font-size: 0.95em;">33 Essential Topics • Quick Reference • Interview Tips</p>
    </div>
</div>

<!-- ==================== TABLE OF CONTENTS ==================== -->
<div class="toc">
    <h2>📋 Table of Contents</h2>
    <div class="toc-grid">
        <div class="toc-item"><span class="num">01</span> <a href="#topic1">Constructor</a></div>
        <div class="toc-item"><span class="num">02</span> <a href="#topic2">Abstract vs Sealed vs Static Class</a></div>
        <div class="toc-item"><span class="num">03</span> <a href="#topic3">Abstract Class vs Interface</a></div>
        <div class="toc-item"><span class="num">04</span> <a href="#topic4">Override vs Overload</a></div>
        <div class="toc-item"><span class="num">05</span> <a href="#topic5">Virtual vs Abstract Method</a></div>
        <div class="toc-item"><span class="num">06</span> <a href="#topic6">Property & Encapsulation</a></div>
        <div class="toc-item"><span class="num">07</span> <a href="#topic7">Static Members (Variable & Method)</a></div>
        <div class="toc-item"><span class="num">08</span> <a href="#topic8">4 Pillars of OOP</a></div>
        <div class="toc-item"><span class="num">09</span> <a href="#topic9">SOLID Principles</a></div>
        <div class="toc-item"><span class="num">10</span> <a href="#topic10">Stored Procedure vs Function</a></div>
        <div class="toc-item"><span class="num">11</span> <a href="#topic11">Indexer in C#</a></div>
        <div class="toc-item"><span class="num">12</span> <a href="#topic12">SQL JOIN Types</a></div>
        <div class="toc-item"><span class="num">13</span> <a href="#topic13">View in SQL</a></div>
        <div class="toc-item"><span class="num">14</span> <a href="#topic14">IEnumerable vs ICollection vs IList vs IQueryable</a></div>
        <div class="toc-item"><span class="num">15</span> <a href="#topic15">First() vs FirstOrDefault() vs Single()</a></div>
        <div class="toc-item"><span class="num">16</span> <a href="#topic16">Code First vs Database First</a></div>
        <div class="toc-item"><span class="num">17</span> <a href="#topic17">EF 6 vs EF Core</a></div>
        <div class="toc-item"><span class="num">18</span> <a href="#topic18">Pagination (Get Only N Rows)</a></div>
        <div class="toc-item"><span class="num">19</span> <a href="#topic19">Lazy Loading vs Eager Loading</a></div>
        <div class="toc-item"><span class="num">20</span> <a href="#topic20">Middleware in ASP.NET Core</a></div>
        <div class="toc-item"><span class="num">21</span> <a href="#topic21">Middleware vs Filters</a></div>
        <div class="toc-item"><span class="num">22</span> <a href="#topic22">Dependency Injection - Service Lifetimes</a></div>
        <div class="toc-item"><span class="num">23</span> <a href="#topic23">MVC Pattern</a></div>
        <div class="toc-item"><span class="num">24</span> <a href="#topic24">HTTP Methods (POST, GET, PUT, DELETE)</a></div>
        <div class="toc-item"><span class="num">25</span> <a href="#topic25">JWT Token Authentication</a></div>
        <div class="toc-item"><span class="num">26</span> <a href="#topic26">CORS (Cross-Origin Resource Sharing)</a></div>
        <div class="toc-item"><span class="num">27</span> <a href="#topic27">Repository Pattern</a></div>
        <div class="toc-item"><span class="num">28</span> <a href="#topic28">Microservices Architecture</a></div>
        <div class="toc-item"><span class="num">29</span> <a href="#topic29">RabbitMQ (Message Broker)</a></div>
        <div class="toc-item"><span class="num">30</span> <a href="#topic30">DDD - Value Objects</a></div>
        <div class="toc-item"><span class="num">31</span> <a href="#topic31">Caching Strategies</a></div>
        <div class="toc-item"><span class="num">32</span> <a href="#topic32">Clean Architecture</a></div>
        <div class="toc-item"><span class="num">33</span> <a href="#topic33">API Versioning</a></div>
        <div class="toc-item"><span class="num">★</span> <a href="#cheatsheet">Quick Reference Cheat Sheet</a></div>
        <div class="toc-item"><span class="num">💡</span> <a href="#tips">Interview Tips</a></div>
    </div>
</div>

<!-- ==================== PART 1: C# & OOP FUNDAMENTALS ==================== -->
<div class="section-header">
    <h2>PART 1: C# & OOP Fundamentals</h2>
    <p>Core concepts every .NET developer must master</p>
</div>

<div class="container">

<!-- TOPIC 1: Constructor -->
<h3 id="topic1">1. What is a Constructor?</h3>

<div class="definition-box">
<strong>Definition:</strong> A Constructor is a special method that runs <strong>automatically</strong> when you create a new object (instance) of a class using the <code>new</code> keyword.
</div>

<h4>Purpose:</h4>
<ul>
    <li>Initialize default values for properties/fields</li>
    <li>Open database connections or file streams</li>
    <li>Load configuration settings</li>
    <li>Set up required resources and dependencies</li>
</ul>

<pre><code>public class Student
{
    public string Name { get; set; }
    public int Age { get; set; }
    
    // Constructor 1: No parameters (Default Constructor)
    public Student()
    {
        Name = "Unknown";
        Age = 0;
        Console.WriteLine("✅ A new student was created!");
    }
    
    // Constructor 2: With parameters (Parameterized)
    public Student(string name, int age)
    {
        Name = name;
        Age = age;
        Console.WriteLine($"✅ Student created: {name}, age {age}");
    }
}

// USAGE:
Student s1 = new Student();              // Uses Constructor 1
// Output: ✅ A new student was created!

Student s2 = new Student("Ahmed", 25);   // Uses Constructor 2
// Output: ✅ Student created: Ahmed, age 25</code></pre>

<table>
<tr><th>Feature</th><th>Description</th></tr>
<tr><td>Name</td><td>Must be exactly the same as the class name</td></tr>
<tr><td>Return Type</td><td>No return type (not even void)</td></tr>
<tr><td>When Called</td><td>Automatically on <code>new ClassName()</code></td></tr>
<tr><td>Overloading</td><td>Yes! Multiple constructors with different parameters allowed</td></tr>
<tr><td><code>this()</code></td><td>Calls another constructor in the same class</td></tr>
<tr><td><code>base()</code></td><td>Calls the parent/base class constructor</td></tr>
</table>

<!-- TOPIC 2: Abstract vs Sealed vs Static -->
<h3 id="topic2" class="page-break">2. Difference Between <code>abstract</code>, <code>sealed</code>, and <code>static</code> Class</h3>

<table>
<tr><th>Type</th><th>What It Means</th><th>Create <code>new</code>?</th><th>Inheritable?</th><th>Best Use Case</th></tr>
<tr>
    <td><strong><code>abstract</code></strong></td>
    <td>Incomplete class - designed to be a base class only</td>
    <td>❌ NO</td>
    <td>✅ YES (must be inherited)</td>
    <td>Base classes like <code>Animal</code>, <code>Shape</code></td>
</tr>
<tr>
    <td><strong><code>sealed</code></strong></td>
    <td>Closed/final class - cannot be extended</td>
    <td>✅ YES</td>
    <td>❌ NO (prevents inheritance)</td>
    <td>Security-sensitive classes, utility wrappers</td>
</tr>
<tr>
    <td><strong><code>static</code></strong></td>
    <td>Utility class - contains only static members</td>
    <td>❌ NO</td>
    <td>❌ NO (cannot be inherited)</td>
    <td>Helper classes like <code>Math</code>, <code>Convert</code>, <code>Console</code></td>
</tr>
</table>

<pre><code>// =============================================
// 1. ABSTRACT CLASS - Must be inherited
// =============================================
public abstract class Shape
{
    public string Color { get; set; }
    
    // Abstract method: No body, MUST be overridden by child class
    public abstract double GetArea();
    
    // Regular method: Has body, optional to override
    public void DisplayColor()
    {
        Console.WriteLine($"Color: {Color}");
    }
}

// ❌ ERROR: Cannot create instance of abstract class
// Shape s = new Shape();  

// ✅ CORRECT: Must inherit it
public class Circle : Shape
{
    public double Radius { get; set; }
    
    // MUST implement all abstract methods
    public override double GetArea()
    {
        return 3.14 * Radius * Radius;
    }
}


// =============================================
// 2. SEALED CLASS - Cannot be inherited
// =============================================
public sealed class ConfigurationManager
{
    public string GetValue(string key) => "some-value";
}

var config = new ConfigurationManager();  // ✅ Works!

// ❌ ERROR: Cannot inherit from sealed class
// class MyConfig : ConfigurationManager { }


// =============================================
// 3. STATIC CLASS - Only static members
// =============================================
public static class MathHelper
{
    // All members MUST be static
    public static int Add(int a, int b) => a + b;
    public static int Multiply(int a, int b) => a * b;
    public static readonly double PI = 3.14159;
}

// ❌ ERROR: Cannot create instance
// MathHelper m = new MathHelper();

// ❌ ERROR: Cannot inherit
// class X : MathHelper { }

// ✅ Call directly on the class:
int sum = MathHelper.Add(5, 3);           // → 8
double area = MathHelper.PI * 5 * 5;      // → 78.54</code></pre>


<!-- TOPIC 3: Abstract Class vs Interface -->
<h3 id="topic3" class="page-break">3. Abstract Class vs Interface</h3>

<table>
<tr><th>Feature</th><th>Abstract Class</th><th>Interface</th></tr>
<tr><td>What is it?</td><td>A partially complete class</td><td>A pure contract/blueprint</td></tr>
<tr><td>Can have fields?</td><td>✅ Yes</td><td>❌ No (C# 8+ has default implementations)</td></tr>
<tr><td>Can have constructor?</td><td>✅ Yes</td><td>❌ No</td></tr>
<tr><td>Can have implementation?</td><td>✅ Yes (full method bodies)</td><td>❌ No (C# 8+ allows defaults)</td></tr>
<tr><td>Access modifiers?</td><td>✅ Any (public, private, protected)</td><td>All members are implicitly public</td></tr>
<tr><td>Multiple inheritance?</td><td>❌ One base class only</td><td>✅ Multiple interfaces allowed</td></tr>
<tr><td>Relationship type</td><td>"IS-A" (is a kind of)</td><td>"CAN-DO" (has capability)</td></tr>
<tr><td>When to use?</td><td>When classes share <strong>common code</strong></td><td>When you need <strong>common behavior contract</strong></td></tr>
</table>

<div class="diagram-box">ABSTRACT CLASS (IS-A relationship):
┌─────────────────────────┐
│     Animal (abstract)   │  ← Has SOME code
│  ─────────────────────  │
│  + Name                 │
│  + Sleep() { ... }      │  ← Has body
│  + MakeSound() [abstract]│ ← No body
└──────────┬──────────────┘
           │
    ┌──────┴──────┬──────────────┐
    ▼             ▼              ▼
┌────────┐  ┌──────────┐  ┌──────────┐
│  Dog   │  │   Cat    │  │   Bird   │
│ Woof!  │  │ Meow!    │  │ Tweet!   │
└────────┘  └──────────┘  └──────────┘


INTERFACE (CAN-DO relationship):
┌─────────────────────────┐
│    ISwimmable           │  ← NO code, just rules
│  ─────────────────────  │
│  + Swim()               │  ← Must implement
│  + Speed { get; set; }  │
└──────────┬──────────────┘
           │
    ┌──────┼──────────────┐
    ▼      ▼              ▼
┌────────┐ ┌────────┐  ┌────────┐
│  Fish  │ │ Human  │  │  Duck  │
│ Swim() │ │ Swim() │  │ Swim() │
└────────┘ └────────┘  └────────┘</div>

<pre><code>// ===== ABSTRACT CLASS EXAMPLE =====
public abstract class Vehicle
{
    public string Brand { get; set; }
    public int Year { get; set; }
    
    // Constructor works in abstract class!
    public Vehicle(string brand, int year)
    {
        Brand = brand;
        Year = year;
    }
    
    // Regular method with implementation
    public void DisplayInfo()
    {
        Console.WriteLine($"{Brand} ({Year})");
    }
    
    // Abstract method - subclasses MUST implement
    public abstract void StartEngine();
}

public class Car : Vehicle
{
    public int Doors { get; set; }
    
    public Car(string brand, int year, int doors) : base(brand, year)
    {
        Doors = doors;
    }
    
    public override void StartEngine()
    {
        Console.WriteLine("Vroom! Car engine started!");
    }
}


// ===== INTERFACE EXAMPLE =====
public interface IFlyable
{
    void Fly();
    double MaxAltitude { get; }
}

public interface ISwimmable
{
    void Swim();
}

// A class can implement MULTIPLE interfaces!
public class Duck : Animal, IFlyable, ISwimmable
{
    public void Fly() => Console.WriteLine("Duck is flying!");
    public void Swim() => Console.WriteLine("Duck is swimming!");
    public double MaxAltitude => 1000;
}</code></pre>


<!-- TOPIC 4: Override vs Overload -->
<h3 id="topic4" class="page-break">4. Override vs Overload</h3>

<table>
<tr><th>Aspect</th><th><code>override</code></th><th><code>overload</code></th></tr>
<tr><td>What does it do?</td><td><strong>Re-implements</strong> a parent's existing method</td><td><strong>Same method name</strong> with different parameters</td></tr>
<tr><td>Keyword required</td><td><code>override</code></td><td>(No special keyword needed)</td></tr>
<tr><td>Requirement</td><td>Parent method must be <code>virtual</code> or <code>abstract</code></td><td>Same name but different parameter signature</td></tr>
<tr><td>Decided at</td><td><strong>Runtime</strong> (Polymorphism)</td><td><strong>Compile-time</strong></td></tr>
<tr><td>Purpose</td><td>Change behavior in child class</td><td>Provide multiple ways to call the same operation</td></tr>
</table>

<pre><code>public class Calculator
{
    // VIRTUAL METHOD - Can be overridden by child classes
    public virtual int Calculate(int a, int b)
    {
        return a + b;  // Default behavior: addition
    }
    
    // OVERLOADED METHODS - Same name, different parameters
    public int Add(int a, int b) => a + b;
    public int Add(int a, int b, int c) => a + b + c;
    public double Add(double a, double b) => a + b;
    public string Add(string a, string b) => a + b;
}

// Child class OVERRIDES the virtual method
public class ScientificCalculator : Calculator
{
    public override int Calculate(int a, int b)
    {
        return a * b;  // Changed behavior: multiplication!
    }
}

// USAGE:
Calculator calc = new Calculator();
Console.WriteLine(calc.Calculate(5, 3));       // → 8 (addition)

ScientificCalculator sciCalc = new ScientificCalculator();
Console.WriteLine(sciCalc.Calculate(5, 3));    // → 15 (multiplication!)

// Overloading usage:
Console.WriteLine(calc.Add(1, 2));             // → 3 (int version)
Console.WriteLine(calc.Add(1, 2, 3));          // → 6 (3 params version)
Console.WriteLine(calc.Add(1.5, 2.5));         // → 4.0 (double version)
Console.WriteLine(calc.Add("Hello", "World")); // → "HelloWorld"</code></pre>


<!-- TOPIC 5: Virtual vs Abstract -->
<h3 id="topic5">5. Virtual Method vs Abstract Method</h3>

<pre><code>public abstract class Animal
{
    // VIRTUAL METHOD:
    // ✓ Has a body (implementation)
    // ✓ Child CAN override (optional choice)
    // ✓ If not overridden, parent's version is used as-is
    public virtual void Sleep()
    {
        Console.WriteLine("Zzzzz... Animal is sleeping");
    }
    
    // ABSTRACT METHOD:
    // ✗ NO body (no implementation at all)
    // ✓ Child MUST override (required - no choice!)
    // ✓ The containing class must be marked 'abstract'
    public abstract void MakeSound();
}

public class Dog : Animal
{
    // Optional: Can choose to override virtual method
    public override void Sleep()
    {
        Console.WriteLine("Dog is sleeping on its cozy bed");
    }
    
    // REQUIRED: Must implement abstract method (compiler enforces this!)
    public override void MakeSound()
    {
        Console.WriteLine("Woof woof!");
    }
}</code></pre>

<table>
<tr><th>Aspect</th><th><code>virtual</code></th><th><code>abstract</code></th></tr>
<tr><td>Has method body?</td><td>✅ Yes, has implementation</td><td>❌ No, just signature</td></tr>
<tr><td>Is overriding mandatory?</td><td>Optional (child's choice)</td><td>Mandatory (child must implement)</td></tr>
<tr><td>Class requirement</td><td>Any class can have virtual methods</td><td>Class must also be <code>abstract</code></td></tr>
</table>


<!-- TOPIC 6: Property & Encapsulation -->
<h3 id="topic6" class="page-break">6. Property & Encapsulation</h3>

<div class="definition-box">
<strong>Encapsulation:</strong> The practice of hiding internal data (fields) and providing controlled access through properties and methods. This protects data integrity and allows validation.
</div>

<pre><code>public class BankAccount
{
    // PRIVATE FIELD - Hidden from outside access
    private double _balance;
    
    // PROPERTY - Controlled gateway for accessing _balance
    public double Balance
    {
        // GETTER: Read value (can include logic)
        get 
        { 
            Console.WriteLine($"Reading balance: {_balance}");
            return _balance; 
        }
        
        // SETTER: Write value (with VALIDATION!)
        set 
        {
            if (value < 0)
            {
                throw new Exception("❌ Error: Balance cannot be negative!");
            }
            if (value > 1000000)
            {
                Console.WriteLine("⚠️ Warning: Large deposit detected!");
            }
            _balance = value;
        }
    }
    
    // READ-ONLY PROPERTY (getter only - no setter)
    public string AccountNumber { get; }  // Can only be set in constructor
    
    // WRITE-ONLY PROPERTY (setter only - rare but possible)
    public string Password { private get; set; }  // Only accessible within the class
}

// USAGE:
var account = new BankAccount();
account.Balance = 1000;     // ✅ Valid - passes validation
account.Balance = -500;     // ❌ Throws exception!
double currentBalance = account.Balance; // ✅ Safe read</code></pre>

<div class="success-box">
<span class="box-title">💡 Why use Properties instead of Public Fields?</span>
<ul>
    <li><strong>Validation:</strong> Reject invalid data before it's stored</li>
    <li><strong>Controlled Access:</strong> Make fields read-only or write-only</li>
    <li><strong>Encapsulation:</strong> Hide implementation details</li>
    <li><strong>Future Flexibility:</strong> Add logic later without breaking external code</li>
</ul>
</div>


<!-- TOPIC 7: Static Members -->
<h3 id="topic7">7. Static Members (Static Variable & Static Method)</h3>

<div class="definition-box">
<strong>Key Concept:</strong> <code>static</code> means <strong>shared among ALL instances</strong> of the class. There is only ONE copy stored in memory, regardless of how many objects you create.
</div>

<pre><code>public class User
{
    // INSTANCE VARIABLE - Each object gets its OWN separate copy
    public string Username { get; set; }
    
    // STATIC VARIABLE - SHARED by all objects (only ONE exists in memory)
    public static int TotalUsersCreated = 0;
    
    // STATIC READONLY - Like a constant, but set at runtime (once)
    public static readonly string SystemName = "MyApp v1.0";
    
    public User(string username)
    {
        Username = username;
        TotalUsersCreated++;  // Increments the SHARED counter
    }
    
    // STATIC METHOD - Can be called WITHOUT creating an object
    public static void DisplaySystemInfo()
    {
        Console.WriteLine($"System: {SystemName}");
        Console.WriteLine($"Total users ever created: {TotalUsersCreated}");
        // Cannot use instance members here!
        // Console.WriteLine(Username);  // ❌ ERROR! Instance member not accessible
    }
    
    // INSTANCE METHOD - Requires an object instance to call
    public void Greet()
    {
        Console.WriteLine($"Hello, I'm {Username}");
        // CAN access static members freely
        Console.WriteLine($"Total users: {TotalUsersCreated}");  // ✅ OK
    }
}

// USAGE:
User u1 = new User("Alice");
User u2 = new User("Bob");
User u3 = new User("Charlie");

Console.WriteLine(User.TotalUsersCreated);  // → 3 (SHARED across all instances!)
User.DisplaySystemInfo();                   // ✅ Works without 'new' keyword

u1.Greet();  // → "Hello, I'm Alice"
u2.Greet();  // → "Hello, I'm Bob"</code></pre>

<table>
<tr><th>Use Case</th><th>Example</th></tr>
<tr><td>Counters</td><td><code>TotalUsersCreated</code>, <code>ConnectionCount</code></td></tr>
<tr><td>Constants</td><td><code>PI</code>, <code>MaxItems</code>, <code>AppVersion</code></td></tr>
<tr><td>Utility methods</td><td><code>Math.Abs()</code>, <code>Convert.ToString()</code>, <code>Guid.NewGuid()</code></td></tr>
<tr><td>Single shared resource</td><td>Database connection string, configuration object</td></tr>
</table>


<!-- TOPIC 8: 4 Pillars of OOP -->
<h3 id="topic8" class="page-break">8. The 4 Pillars of Object-Oriented Programming</h3>

<div class="key-points">
    <div class="key-point">
        <strong>1. ENCAPSULATION 🔒</strong>
        Hide data and protect it<br>
        <code>private</code> fields + Properties
    </div>
    <div class="key-point">
        <strong>2. INHERITANCE 🔄</strong>
        Reuse code from parent<br>
        <code>class Dog : Animal</code>
    </div>
    <div class="key-point">
        <strong>3. POLYMORPHISM 🎭</strong>
        Same interface, different behaviors<br>
        <code>virtual</code>/<code>override</code>
    </div>
    <div class="key-point">
        <strong>4. ABSTRACTION 🙈</strong>
        Hide complexity<br>
        <code>abstract</code> class / Interface
    </div>
</div>

<pre><code>// 1️⃣ ENCAPSULATION (Data Hiding)
private int age;                          // Hidden field
public int Age { get { return age; } }    // Safe property access

// 2️⃣ INHERITANCE (Code Reuse)
class Animal { public void Eat() {} }
class Dog : Animal { }                     // Dog inherits Eat()

// 3️⃣ POLYMORPHISM (Many Forms)
animal.MakeSound();  // Dog says "Woof!", Cat says "Meow!"

// 4️⃣ ABSTRACTION (Hide Complexity)
car.Start();        // User doesn't know HOW engine starts internally</code></pre>


<!-- TOPIC 9: SOLID Principles -->
<h3 id="topic9">9. SOLID Principles</h3>

<table>
<tr><th>Letter</th><th>Principle</th><th>Simple Explanation</th><th>Bad Example</th><th>Good Example</th></tr>
<tr>
    <td><strong>S</strong></td>
    <td><strong>Single Responsibility</strong></td>
    <td>Each class should have <strong>ONE reason to change</strong></td>
    <td><code>User</code> saves to DB, sends email, generates PDF</td>
    <td><code>UserService</code>, <code>EmailService</code>, <code>ReportService</code></td>
</tr>
<tr>
    <td><strong>O</strong></td>
    <td><strong>Open/Closed Principle</strong></td>
    <td>Open for extension, closed for modification</td>
    <td>Modifying existing working code to add feature</td>
    <td>Adding new class that implements an interface</td>
</tr>
<tr>
    <td><strong>L</strong></td>
    <td><strong>Liskov Substitution</strong></td>
    <td>Child objects must be replaceable with parent objects</td>
    <td><code>Square</code> breaking <code>Rectangle</code> behavior</td>
    <td><code>List&lt;T&gt;</code> replacing <code>IList&lt;T&gt;</code></td>
</tr>
<tr>
    <td><strong>I</strong></td>
    <td><strong>Interface Segregation</strong></td>
    <td>Many small, specific interfaces > one giant interface</td>
    <td><code>IMachine</code> with Print(), Scan(), Fax(), Cook()</td>
    <td><code>IPrinter</code>, <code>IScanner</code>, <code>IFaxMachine</code></td>
</tr>
<tr>
    <td><strong>D</strong></td>
    <td><strong>Dependency Inversion</strong></td>
    <td>Depend on abstractions, not concrete details</td>
    <td>Depending directly on <code>SqlRepository</code></td>
    <td>Depending on <code>IRepository</code> interface</td>
</tr>
</table>

<pre><code>// ❌ BAD - Single class doing too many things (violates SRP)
public class User
{
    public string Name { get; set; }
    
    public void SaveToDatabase() { /* SQL INSERT code */ }
    public void SendWelcomeEmail() { /* SMTP email code */ }
    public void GeneratePDFReport() { /* PDF generation code */ }
    public void ValidateInput() { /* validation logic */ }
}

// ✅ GOOD - Each class has one clear responsibility
// Domain Layer
public class User { public string Name { get; set; } }

// Data Access Layer
public class UserRepository 
{ 
    public void Save(User u) { /* Database logic */ } 
}

// Infrastructure Layer
public class EmailService 
{ 
    public async Task SendWelcomeAsync(User u) { /* Email logic */ } 
}

// Application Layer
public class ReportService 
{ 
    public byte[] GenerateUserReport(User u) { /* PDF logic */ } 
}</code></pre>

</div><!-- End Part 1 Container -->

<!-- ==================== PART 2: DATABASE & ENTITY FRAMEWORK ==================== -->
<div class="section-header page-break">
    <h2>PART 2: Database & Entity Framework</h2>
    <p>Data access patterns and ORM fundamentals</p>
</div>

<div class="container">

<!-- TOPIC 10: Stored Procedure vs Function -->
<h3 id="topic10">10. Stored Procedure vs Function</h3>

<table>
<tr><th>Feature</th><th>Stored Procedure</th><th>Function</th></tr>
<tr><td>Return value(s)</td><td>0 or more values (tables, integers, output params)</td><td><strong>Must return</strong> single scalar value OR table</td></tr>
<tr><td>Parameters</td><td>INPUT, OUTPUT, INPUT_OUTPUT supported</td><td>INPUT parameters only</td></tr>
<tr><td>Use in SELECT statement</td><td>❌ Cannot be used in SELECT</td><td>✅ Can be used directly in SELECT/WHERE</td></tr>
<tr><td>Modify data (DML)</td><td>✅ INSERT, UPDATE, DELETE allowed</td><td>❌ Read-only (no modifications)</td></tr>
<tr><td>Error handling</td><td>Full TRY-CATCH support</td><td>Limited error handling capabilities</td></tr>
<tr><td>Call from application</td><td><code>EXEC</code> command</td><td>Like any expression/column</td></tr>
</table>

<pre><code>-- STORED PROCEDURE
CREATE PROCEDURE GetUserById
    @UserId INT
AS
BEGIN
    SELECT Id, Name, Email, CreatedDate
    FROM Users
    WHERE Id = @UserId
END

-- Call it:
EXEC GetUserById @UserId = 5;


-- FUNCTION (Scalar - returns single value)
CREATE FUNCTION GetUserEmail
    @UserId INT
RETURNS VARCHAR(100)
AS
BEGIN
    DECLARE @Email VARCHAR(100)
    SELECT @Email = Email FROM Users WHERE Id = @UserId
    RETURN @Email
END

-- Call it (can be used inside SELECT!):
SELECT dbo.GetUserEmail(5);
SELECT *, dbo.GetUserEmail(Id) AS UserEmail FROM Orders;


-- FUNCTION (Table-valued - returns entire table)
CREATE FUNCTION GetUsersByRole
    @RoleName NVARCHAR(50)
RETURNS TABLE
AS
RETURN
(
    SELECT Id, Name, Email FROM Users WHERE Role = @RoleName
)

-- Usage:
SELECT * FROM GetUsersByRole('Admin');</code></pre>


<!-- TOPIC 11: Indexer -->
<h3 id="topic11" class="page-break">11. Indexer in C#</h3>

<div class="definition-box">
<strong>Definition:</strong> An indexer allows a class to be accessed like an array using square brackets <code>[]</code>. It uses the <code>this</code> keyword and enables custom index-based access to class data.
</div>

<pre><code>public class StudentGrades
{
    private Dictionary&lt;string, int&gt; _grades = new Dictionary&lt;string, int&gt;();
    
    // INDEXER definition - uses 'this' keyword
    public int this[string subjectName]
    { 
        get 
        { 
            if (_grades.ContainsKey(subjectName))
                return _grades[subjectName];
            return 0; // Default if subject not found
        } 
        set 
        { 
            _grades[subjectName] = value; 
        } 
    }
    
    // Overloaded indexer with integer index
    public int this[int index]
    {
        get { return _grades.Values.ElementAtOrDefault(index); }
    }
}

// USAGE - Looks exactly like array access!
var grades = new StudentGrades();

// SET values using indexer
grades["Math"] = 95;
grades["English"] = 88;
grades["Science"] = 92;

// GET values using indexer
int mathScore = grades["Math"];        // → 95
int englishScore = grades["English"];  // → 88
int historyScore = grades["History"];  // → 0 (not found, returns default)

// Using integer indexer
int firstGrade = grades[0];            // → 95 (first item in dictionary)</code></pre>


<!-- TOPIC 12: SQL JOIN Types -->
<h3 id="topic12" class="page-break">12. SQL JOIN Types</h3>

<table>
<tr><th>Join Type</th><th>Description</th><th>Venn Diagram Concept</th><th>NULL Handling</th></tr>
<tr>
    <td><strong>INNER JOIN</strong></td>
    <td>Returns only rows where there's a match in BOTH tables</td>
    <td>Intersection (A ∩ B)</td>
    <td>No NULLs - unmatched rows excluded</td>
</tr>
<tr>
    <td><strong>LEFT JOIN</strong></td>
    <td>All rows from LEFT table + matching rows from RIGHT table</td>
    <td>Entire Left circle + intersection</td>
    <td>Right columns show NULL when no match</td>
</tr>
<tr>
    <td><strong>RIGHT JOIN</strong></td>
    <td>All rows from RIGHT table + matching rows from LEFT table</td>
    <td>Entire Right circle + intersection</td>
    <td>Left columns show NULL when no match</td>
</tr>
<tr>
    <td><strong>FULL OUTER JOIN</strong></td>
    <td>All rows from BOTH tables, matched and unmatched</td>
    <td>Union (A ∪ B)</td>
    <td>NULLs appear wherever no match exists</td>
</tr>
</table>

<pre><code>-- INNER JOIN: Only matching records (most common)
SELECT u.Name, o.Amount, o.OrderDate
FROM Users u
INNER JOIN Orders o ON u.Id = o.UserId;

-- LEFT JOIN: All users, even those without orders
SELECT u.Name, COUNT(o.Id) AS OrderCount
FROM Users u
LEFT JOIN Orders o ON u.Id = o.UserId
GROUP BY u.Id, u.Name;
-- Users without orders will show OrderCount = 0 (or NULL)

-- LEFT JOIN with ISNULL/COALESCE for cleaner output
SELECT u.Name, ISNULL(COUNT(o.Id), 0) AS OrderCount
FROM Users u
LEFT JOIN Orders o ON u.Id = o.UserId
GROUP BY u.Id, u.Name;</code></pre>

<div class="diagram-box">TABLE A (Users)          TABLE B (Orders)
┌──────┬────────┐        ┌──────┬─────────┐
│  ID  │  Name  │        │ UserID│ Amount  │
├──────┼────────┤        ├──────┼─────────┤
│  1   │ Alice  │        │  1   │   $100  │
│  2   │ Bob    │        │  1   │   $200  │
│  3   │ Charlie│        │  3   │   $150  │
│  4   │ Diana  │        │  99  │   $500  │  ← orphan record
└──────┴────────┘        └──────┴─────────┘

INNER JOIN result:         LEFT JOIN result:
┌──────┬────────┬────────┐  ┌──────┬────────┬────────┐
│  ID  │  Name  │ Amount │  │  ID  │  Name  │ Amount │
├──────┼────────┼────────┤  ├──────┼────────┼────────┤
│  1   │ Alice  │  $100  │  │  1   │ Alice  │  $100  │
│  1   │ Alice  │  $200  │  │  1   │ Alice  │  $200  │
│  3   │Charlie │  $150  │  │  2   │ Bob    │  NULL  │  ← no orders
└──────┴────────┴────────┘  │  3   │Charlie │  $150  │
(Matching rows ONLY)        │  4   │ Diana  │  NULL  │  ← no orders
                            └──────┴────────┴────────┘
                           (All from left + matches from right)</div>


<!-- TOPIC 13: View -->
<h3 id="topic13">13. View in SQL</h3>

<div class="definition-box">
<strong>Definition:</strong> A View is a <strong>saved query</strong> (virtual table) that looks and behaves like a real table but contains data retrieved dynamically from one or more underlying tables.
</div>

<div class="info-box">
<span class="box-title">Why Use Views?</span>
<ul>
    <li><strong>Simplify complex queries</strong>: Instead of writing a 20-line JOIN repeatedly, use one view name</li>
    <li><strong>Security</strong>: Grant access to view while hiding sensitive columns (Salary, SSN, PasswordHash)</li>
    <li><strong>Abstraction</strong>: Rename columns for clarity without changing actual schema</li>
    <li><strong>Reusability</strong>: One view used in multiple places (reports, APIs, other views)</li>
</ul>
</div>

<pre><code>-- Creating a VIEW
CREATE VIEW vw_EmployeeDetails AS
SELECT 
    e.Id,
    e.FirstName + ' ' + e.LastName AS FullName,
    d.DepartmentName,
    s.Salary,
    s.HireDate,
    CASE 
        WHEN s.Salary > 80000 THEN 'Senior'
        WHEN s.Salary > 50000 THEN 'Mid-Level'
        ELSE 'Junior'
    END AS SeniorityLevel
FROM Employees e
JOIN Departments d ON e.DepartmentId = d.Id
JOIN Salaries s ON e.Id = s.EmployeeId
WHERE s.IsActive = 1

-- Using the VIEW (exactly like a real table!)
SELECT * FROM vw_EmployeeDetails WHERE Salary > 60000;

-- Views can reference other views!
CREATE VIEW vw_SeniorEmployees AS
SELECT * FROM vw_EmployeeDetails WHERE SeniorityLevel = 'Senior';

-- Update through view (sometimes allowed - depends on complexity)
UPDATE vw_EmployeeDetails SET Salary = 75000 WHERE Id = 5;

-- Drop a view
DROP VIEW IF EXISTS vw_EmployeeDetails;</code></pre>


<!-- TOPIC 14: Collection Interfaces -->
<h3 id="topic14" class="page-break">14. IEnumerable vs ICollection vs IList vs IQueryable</h3>

<table>
<tr><th>Interface</th><th>Key Features</th><th>Common Implementations</th><th>Best Used For</th></tr>
<tr>
    <td><strong>IEnumerable&lt;T&gt;</strong></td>
    <td>• Basic iteration (foreach)<br>• Forward-only traversal<br>• Read-only access<br>• LINQ to Objects execution</td>
    <td>Arrays, Lists, most collections</td>
    <td>Simple iteration over in-memory data</td>
</tr>
<tr>
    <td><strong>ICollection&lt;T&gt;</strong></td>
    <td>• Everything in IEnumerable<br>• <strong>Add()</strong> / <strong>Remove()</strong><br>• <strong>Count</strong> property<br>• Contains(), Clear()</td>
    <td>List&lt;T&gt;, HashSet&lt;T&gt;, Collection&lt;T&gt;</td>
    <td>When you need to modify collection contents</td>
</tr>
<tr>
    <td><strong>IList&lt;T&gt;</strong></td>
    <td>• Everything in ICollection<br>• <strong>Indexer [i]</strong> access<br>• Insert(i), RemoveAt(i)<br>• Array-style random access</td>
    <td>List&lt;T&gt;, Array (via wrapper)</td>
    <td>When you need index-based access to elements</td>
</tr>
<tr>
    <td><strong>IQueryable&lt;T&gt;</strong></td>
    <td>• Builds expression trees<br>• Executes in <strong>database</strong> (LINQ-to-SQL)<br>• Deferred execution<br>• Provider translates to SQL</td>
    <td>Entity Framework DbSets</td>
    <td>Database queries with EF/LINQ - optimal performance!</td>
</tr>
</table>

<pre><code>// IEnumerable - Basic iteration (executes IN MEMORY)
IEnumerable&lt;User&gt; users = dbContext.Users.ToList().Where(u =&gt; u.Age &gt; 20);
// SQL executed: SELECT * FROM Users (ALL data loaded into memory first!)
// Then filtered in memory - potentially slow for large datasets

// IQueryable - Query building (executes in DATABASE)
IQueryable&lt;User&gt; query = dbContext.Users.Where(u =&gt; u.Age &gt; 20);
// SQL will be: SELECT * FROM Users WHERE Age &gt; 20
// Filter happens in DATABASE! Much faster and more efficient!

// When you ACTUALLY need the data (materialize):
var results = await query.ToListAsync();  // Now SQL runs

// ICollection example:
ICollection&lt;string&gt; names = new List&lt;string&gt;();
names.Add("Alice");       // ✅ Allowed
names.Remove("Bob");      // ✅ Allowed
names.Count;               // ✅ Available
// names[0];               // ❌ Not available in ICollection

// IList example:
IList&lt;string&gt; list = new List&lt;string&gt;();
list.Add("Alice");
list[0] = "Bob";           // ✅ Indexer available
list.Insert(0, "First");   // ✅ Insert at position</code></pre>


<!-- TOPIC 15: First vs FirstOrDefault etc -->
<h3 id="topic15" class="page-break">15. First() vs FirstOrDefault() vs Single() vs SingleOrDefault()</h3>

<table>
<tr><th>Method</th><th>Returns if FOUND</th><th>Returns if NOT Found</th><th>If MULTIPLE found</th><th>Best For</th></tr>
<tr>
    <td><code>First()</code></td>
    <td>First matching item</td>
    <td>❌ <strong>Throws Exception!</strong></td>
    <td>Returns first item</td>
    <td>When you're 100% sure item exists</td>
</tr>
<tr>
    <td><code>FirstOrDefault()</code></td>
    <td>First matching item</td>
    <td><strong>null / default(T)</strong></td>
    <td>Returns first item</td>
    <td><strong>Most common!</strong> Safe option</td>
</tr>
<tr>
    <td><code>Single()</code></td>
    <td>The one item</td>
    <td>❌ <strong>Throws Exception!</strong></td>
    <td>❌ <strong>Throws Exception!</strong></td>
    <td>When expecting EXACTLY one item</td>
</tr>
<tr>
    <td><code>SingleOrDefault()</code></td>
    <td>The one item</td>
    <td><strong>null / default(T)</strong></td>
    <td>❌ <strong>Throws Exception!</strong></td>
    <td>Safe exact-one lookup</td>
</tr>
</table>

<pre><code>// Scenario: Looking for user with ID = 5

// FIRST - Gets first match (even if many exist)
var user = context.Users.First(u =&gt;u.Role == "Admin");
// If no Admins exist → InvalidOperationException!

// FIRSTORDEFAULT - Safe version (returns null if not found)
var user = context.Users.FirstOrDefault(u =&gt; u.Id == 999);
if (user == null)
{
    Console.WriteLine("User not found");  // Handle gracefully
}
else
{
    Console.WriteLine($"Found: {user.Name}");
}

// SINGLE - Expects EXACTLY ONE match (throws if 0 or 2+)
var config = context.Configs.Single(c =&gt; c.Key == "Theme");
// If 0 configs or 2+ configs with key "Theme" → Exception!

// SINGLEORDEFAULT - Safe exact-one lookup
var config = context.Configs.SingleOrDefault(c =&gt; c.Key == "Theme");
if (config == null)
{
    // Create default config...
    config = new Config { Key = "Theme", Value = "Light" };
    context.Configs.Add(config);
}</code></pre>

<div class="success-box">
<span class="box-title">💡 Pro Tip:</span>
Always prefer <code>FirstOrDefault()</code> over <code>First()</code> unless you specifically want an exception when no results are found. This makes your code more robust and prevents crashes from empty datasets.
</div>


<!-- TOPIC 16: Code First vs DB First -->
<h3 id="topic16" class="page-break">16. Entity Framework: Code First vs Database First</h3>

<div class="comparison">
<div class="compare-col good">
<h5>✅ CODE FIRST APPROACH</h5>
<p><strong>Flow:</strong> Write C# Classes → Run Migration → Database Created</p>
<ol>
<li>Define model classes (POCOs)</li>
<li>Create DbContext</li>
<li>Run: <code>add-migration InitialCreate</code></li>
<li>Run: <code>update-database</code></li>
</ol>
<p><strong>Pros:</strong> Version control friendly, great for new projects, easy refactoring</p>
</div>
<div class="compare-col">
<h5>🗄️ DATABASE FIRST APPROACH</h5>
<p><strong>Flow:</strong> Design Database → Reverse Engineer → C# Classes Generated</p>
<ol>
<li>Design tables in SSMS/Azure Data Studio</li>
<li>Run: <code>Scaffold-DbContext</code></li>
<li>Classes auto-generated</li>
<li>Customize as needed</li>
</ol>
<p><strong>Pros:</strong> Great for legacy DBs, DBAs have full control</p>
</div>
</div>

<pre><code>// ========== CODE FIRST EXAMPLE ==========

// STEP 1: Define your model classes (POCOs)
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Price { get; set; }
    public int CategoryId { get; set; }
    
    // Navigation property
    public Category Category { get; set; }
}

public class Category
{
    public int Id { get; set; }
    public string Name { get; set; }
    public ICollection&lt;Product&gt; Products { get; set; }
}

// STEP 2: Create DbContext
public class AppDbContext : DbContext
{
    public DbSet&lt;Product&gt; Products { get; set; }
    public DbSet&lt;Category&gt; Categories { get; set; }
    
    protected override void OnConfiguring(DbContextOptionsBuilder options)
    {
        options.UseSqlServer("Server=.;Database=MyDb;Trusted_Connection=True;");
    }
    
    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        // Fluent API configurations here
        modelBuilder.Entity&lt;Product&gt;()
            .HasOne(p =&gt; p.Category)
            .WithMany(c =&gt; c.Products)
            .HasForeignKey(p =&gt; p.CategoryId);
    }
}

// STEP 3 & 4: Run in Package Manager Console
// > add-migration InitialCreate
// > update-database
// Result: Database and tables are created automatically!</code></pre>


<!-- TOPIC 17: EF 6 vs EF Core -->
<h3 id="topic17">17. EF 6 vs EF Core</h3>

<table>
<tr><th>Feature</th><th>Entity Framework 6</th><th>Entity Framework Core</th></tr>
<tr><td>Target Framework</td><td>.NET Framework only (Windows)</td><td>.NET Core, .NET 5/6/7/8+, .NET Framework</td></tr>
<tr><td>Performance</td><td>Baseline (slower)</td><td><strong>Up to 10x faster</strong></td></tr>
<tr><td>Cross-Platform</td><td>Windows only</td><td>Windows, Linux, macOS (Docker ready)</td></tr>
<tr><td>Async Support</td><td>Limited async operations</td><td><strong>Full async support</strong> throughout</td></tr>
<tr><td>DI Integration</td><td>Manual setup required</td><td><strong>Built-in DI container</strong></td></tr>
<tr><td>Batch Updates</td><td>❌ Sends updates one-by-one</td><td>✅ Sends in batches (much faster)</td></tr>
<tr><td>Shadow Properties</td><td>❌ Not available</td><td>✅ Properties not in entity class</td></tr>
<tr><td>Global Query Filters</td><td>❌ Not available</td><td>✅ Auto-filters (soft delete, multi-tenant)</td></tr>
<tr><td>Future Status</td><td>Maintenance mode only</td><td><strong>Active development</strong></td></tr>
</table>

<pre><code>// ========== EF CORE EXCLUSIVE FEATURES ==========

// 1. Async Operations (full support)
public async Task&lt;User&gt; GetUserAsync(int id)
{
    return await _context.Users.FindAsync(id);
}

// 2. Shadow Properties (properties stored in DB but NOT in C# class)
context.Entry(user).Property("CreatedAt").CurrentValue = DateTime.Now;
context.Entry(user).Property("CreatedBy").CurrentValue = "System";

// 3. Global Query Filters (automatic filtering on EVERY query)
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.Entity&lt;Post&gt;().HasQueryFilter(p =&gt; !p.IsDeleted);
    // Now ALL queries automatically exclude deleted posts!
    var posts = await _context.Posts.ToListAsync(); 
    // Generates: SELECT ... FROM Posts WHERE IsDeleted = 0
}

// 4. Batch Updates (EF Core 7+) - executes as single SQL statement!
await _context.Products
    .Where(p =&gt; p.Price &lt; 10)
    .ExecuteUpdateAsync(setters =&gt; setters.SetProperty(p =&gt; p.IsDiscontinued, true));
// Generates: UPDATE Products SET IsDiscontinued = 1 WHERE Price &lt; 10

// 5. Split Query (for complex queries with multiple includes)
var orders = await _context.Orders
    .Include(o =&gt; o.Customer)
    .Include(o =&gt; o.Items)
        .ThenInclude(i =&gt; i.Product)
    .AsSplitQuery()  // Generates multiple efficient SQL queries
    .ToListAsync();</code></pre>


<!-- TOPIC 18: Pagination -->
<h3 id="topic18" class="page-break">18. Pagination (Get Only N Rows)</h3>

<div class="info-box">
<span class="box-title">Why Paginate?</span>
<ul>
    <li><strong>Performance:</strong> Don't load 1 million rows into memory!</li>
    <li><strong>Bandwidth:</strong> Less data transferred over network</li>
    <li><strong>Memory:</strong> Lower server memory consumption</li>
    <li><strong>UX:</strong> Faster page loads, better user experience</li>
</ul>
</div>

<pre><code>// PAGINATION SERVICE
public class ProductService
{
    private readonly AppDbContext _context;
    
    public ProductService(AppDbContext context) =&gt; _context = context;
    
    public async Task&lt;PagedResult&lt;Product&gt;&gt; GetProductsAsync(
        int pageNumber = 1, 
        int pageSize = 10)
    {
        var query = _context.Products.OrderBy(p =&gt; p.Id);
        
        // Total count (for showing "Page 1 of 50")
        var totalCount = await query.CountAsync();
        
        // The actual page of data
        var items = await query
            .Skip((pageNumber - 1) * pageSize)  // Skip previous pages' data
            .Take(pageSize)                      // Take only 'pageSize' items
            .ToListAsync();
            
        return new PagedResult&lt;Product&gt;
        {
            Items = items,
            PageNumber = pageNumber,
            PageSize = pageSize,
            TotalCount = totalCount,
            TotalPages = (int)Math.Ceiling(totalCount / (double)pageSize),
            HasPreviousPage = pageNumber &gt; 1,
            HasNextPage = pageNumber * pageSize &lt; totalCount
        };
    }
}

// Response DTO
public class PagedResult&lt;T&gt;
{
    public IEnumerable&lt;T&gt; Items { get; set; }
    public int PageNumber { get; set; }
    public int PageSize { get; set; }
    public int TotalCount { get; set; }
    public int TotalPages { get; set; }
    public bool HasPreviousPage { get; set; }
    public bool HasNextPage { get; set; }
}

// CONTROLLER
[HttpGet]
public async Task&lt;IActionResult&gt; GetProducts(
    [FromQuery] int page = 1, 
    [FromQuery] int size = 10)
{
    var result = await _service.GetProductsAsync(page, size);
    return Ok(new 
    { 
        result.Items, 
        result.PageNumber, 
        result.TotalPages,
        result.TotalCount,
        result.HasNextPage,
        result.HasPreviousPage
    });
}

// API CALLS:
// GET /api/products?page=1&amp;size=10   → Items 1-10
// GET /api/products?page=2&amp;size=10   → Items 11-20
// GET /api/products?page=5&amp;size=20   → Items 81-100</code></pre>


<!-- TOPIC 19: Lazy vs Eager Loading -->
<h3 id="topic19" class="page-break">19. Lazy Loading vs Eager Loading</h3>

<table>
<tr><th>Aspect</th><th>Lazy Loading</th><th>Eager Loading</th></tr>
<tr><td>When data loads</td><td>When you ACCESS the navigation property</td><td><strong>Immediately</strong> with the main query</td></tr>
<tr><td>How to enable</td><td><code>virtual</code> navigation properties + proxy</td><td><code>.Include()</code> / <code>.ThenInclude()</code></td></tr>
<tr><td>SQL queries generated</td><td><strong>Multiple</strong> (N+1 problem risk)</td><td><strong>One</strong> (with JOINs)</td></tr>
<tr><td>When to use</td><td>When you might NOT need related data</td><td>When you KNOW you'll need related data</td></tr>
<tr><td>Performance</td><td>Can be very slow (many round-trips)</td><td>Usually faster (single optimized query)</td></tr>
<tr><td>Memory usage</td><td>Loads only what you actually use</td><td>May load more than immediately needed</td></tr>
</table>

<pre><code>// =============================================
// LAZY LOADING (Default with 'virtual')
// =============================================
public class Order
{
    public int Id { get; set; }
    public DateTime OrderDate { get; set; }
    
    // VIRTUAL enables lazy loading proxy
    public virtual ICollection&lt;OrderItem&gt; Items { get; set; }
    public virtual Customer Customer { get; set; }
}

// WHAT HAPPENS:
var order = _context.Orders.First(o =&gt; o.Id == 1);
// SQL #1: SELECT * FROM Orders WHERE Id = 1

foreach (var item in order.Items)
{
    Console.WriteLine(item.ProductName);
}
// SQL #2: SELECT * FROM OrderItems WHERE OrderId = 1  ← Loaded NOW!

// ⚠️ THE N+1 PROBLEM:
var orders = _context.Orders.ToList();           // SQL #1: All orders
foreach (var order in orders)
{
    foreach (var item in order.Items)             // SQL per order!
    { }
}
// For 100 orders = 101 SQL queries! 🐌 Very slow!


// =============================================
// EAGER LOADING (Recommended for most cases)
// =============================================
var order = _context.Orders
    .Include(o =&gt; o.Items)           // ← Include tells EF to JOIN
    .Include(o =&gt; o.Customer)        // ← Include another relation
    .FirstOrDefault(o =&gt; o.Id == 1);

// SQL #1 (ONLY ONE QUERY):
// SELECT o.*, i.*, c.* 
// FROM Orders o
// LEFT JOIN OrderItems i ON o.Id = i.OrderId
// LEFT JOIN Customers c ON o.CustomerId = c.Id
// WHERE o.Id = 1

// Now accessing Items doesn't trigger new queries!
foreach (var item in order.Items)   // Already loaded! ✅
{
    Console.WriteLine(item.ProductName);
}

// Multiple levels (ThenInclude):
var orders = _context.Orders
    .Include(o =&gt; o.Items)
        .ThenInclude(i =&gt; i.Product)  // Items → Product
    .Include(o =&gt; o.Customer)
        .ThenInclude(c =&gt; c.Address)  // Customer → Address
    .ToList();</code></pre>

</div><!-- End Part 2 Container -->


<!-- ==================== PART 3: ASP.NET CORE & WEB APIs ==================== -->
<div class="section-header page-break">
    <h2>PART 3: ASP.NET Core & Web APIs</h2>
    <p>Building modern web applications and RESTful services</p>
</div>

<div class="container">

<!-- TOPIC 20: Middleware -->
<h3 id="topic20">20. Middleware in ASP.NET Core</h3>

<div class="definition-box">
<strong>Definition:</strong> Middleware components are assembled into an application pipeline to handle requests and responses. Each component can decide whether to pass the request to the next component and perform actions before/after the next component.
</div>

<div class="diagram-box">HTTP Request Arrives
        ↓
┌─────────────────────────────────────────────────┐
│  Middleware 1: Exception Handler                │  ← Catches errors globally
│  [Try-Catch wrapper around everything]          │
└──────────────────────┬──────────────────────────┘
                       ↓
┌─────────────────────────────────────────────────┐
│  Middleware 2: HTTPS Redirection                 │  ← Forces HTTPS
│  [http:// → https redirect]                     │
└──────────────────────┬──────────────────────────┘
                       ↓
┌─────────────────────────────────────────────────┐
│  Middleware 3: Static Files                     │  ← Serves CSS, JS, images
│  [wwwroot folder serving]                       │
└──────────────────────┬──────────────────────────┘
                       ↓
┌─────────────────────────────────────────────────┐
│  Middleware 4: Routing                          │  ← URL matching
│  [MapControllers()]                              │
└──────────────────────┬──────────────────────────┘
                       ↓
┌─────────────────────────────────────────────────┐
│  Middleware 5: Authentication (JWT/Cookies)      │  ← Validates token
│  [Check Authorization header]                   │
└──────────────────────┬──────────────────────────┘
                       ↓
              HTTP Response Sent Back</div>

<pre><code>// Program.cs - Middleware Pipeline Configuration
var app = builder.Build();

// 1. Custom Logging Middleware (runs on EVERY request)
app.Use(async (context, next) =&gt;
{
    // Request processing START
    Console.WriteLine($"\u2192 {context.Request.Method} {context.Request.Path}");
    var stopwatch = System.Diagnostics.Stopwatch.StartNew();
    
    await next.Invoke(); // Pass control to NEXT middleware
    
    // Response processing END
    stopwatch.Stop();
    Console.WriteLine($"\u2190 {context.Response.StatusCode} ({stopwatch.ElapsedMilliseconds}ms)");
});

// 2. Exception Handling (should be early in pipeline)
app.UseExceptionHandler("/error");

// 3. Development error pages
if (app.Environment.IsDevelopment())
{
    app.UseDeveloperExceptionPage();
}

// 4. HTTPS enforcement
app.UseHttpsRedirection();

// 5. Static files (CSS, JS, images)
app.UseStaticFiles();

// 6. URL routing
app.UseRouting();

// 7. Authentication & Authorization
app.UseAuthentication();
app.UseAuthorization();

// 8. Map endpoint routes (MUST come after UseRouting)
app.MapControllers();

// 9. Terminal middleware (catches unmatched routes)
app.Run(async (context) =&gt;
{
    context.Response.StatusCode = 404;
    await context.Response.WriteAsync("{ \"error\": \"Page not found\" }");
});

app.Run();</code></pre>

<div class="warning-box">
<span class="box-title">⚠️ Important: Middleware Order Matters!</span>
The order in which you register middleware is critical. For example, authentication middleware must run before authorization middleware, and both must run before your endpoint mapping.
</div>


<!-- TOPIC 21: Middleware vs Filters -->
<h3 id="topic21" class="page-break">21. Middleware vs Filters</h3>

<table>
<tr><th>Aspect</th><th>Middleware</th><th>Filters</th></tr>
<tr><td><strong>Scope</strong></td>
    <td><strong>Entire application</strong> - intercepts ALL requests including static files, images, API calls</td>
    <td><strong>MVC/Razor only</strong> - only controller action executions</td>
</tr>
<tr><td><strong>What it intercepts</strong></td>
    <td>Raw HttpContext (any HTTP request/response)</td>
    <td>ActionExecutingContext (MVC-specific context with model binding info)</td>
</tr>
<tr><td><strong>Where configured</strong></td>
    <td><code>Program.cs</code> pipeline (<code>app.UseXxx()</code>)</td>
    <td>As <code>[Attributes]</code> on controllers/actions or global registration</td>
</tr>
<tr><td><strong>Access to</strong></td>
    <td>HttpContext (raw request/response stream)</td>
    <td>Action arguments, ModelState, IActionResult, Controller instance</td>
</tr>
<tr><td><strong>Common examples</strong></td>
    <td>Authentication, CORS, Compression, Logging, Static files</td>
    <td>[Authorize], [ValidateAntiforgeryToken], Action logging, Caching, Validation</td>
</tr>
</table>

<pre><code>// ========== MIDDLEWARE (Global Level) ==========
// Runs for EVERY request to your app (including non-MVC requests)
public class RequestLoggingMiddleware
{
    private readonly RequestDelegate _next;
    
    public RequestLoggingMiddleware(RequestDelegate next)
    {
        _next = next;
    }
    
    public async Task InvokeAsync(HttpContext context)
    {
        // Runs for: GET /api/users, GET /styles.css, /favicon.ico, etc.
        LogRequest(context.Request);
        
        await _next(context); // Continue pipeline
        
        LogResponse(context.Response);
    }
}
// Registration: app.UseMiddleware&lt;RequestLoggingMiddleware&gt;();


// ========== FILTER (Action Level) ==========
// Runs ONLY for MVC controller action methods
public class LogActionFilter : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        // Only runs for: [HttpGet] actions in Controllers
        var controller = context.Controller.GetType().Name;
        var action = context.ActionDescriptor.RouteValues["action"];
        Log($"{controller}.{action} called");
    }
    
    public override void OnActionExecuted(ActionExecutedContext context)
    {
        Log($"Action completed: {context.HttpContext.Response.StatusCode}");
    }
}
// Usage: [LogActionFilter] attribute on controller or action</code></pre>


<!-- TOPIC 22: Dependency Injection Lifetimes -->
<h3 id="topic22" class="page-break">22. Dependency Injection - Service Lifetimes</h3>

<div class="definition-box">
<strong>Dependency Injection (DI):</strong> Instead of creating dependencies with <code>new</code>, they are provided (injected) to your class via constructor or properties. This promotes loose coupling and easier testing.
</div>

<table>
<tr><th>Lifetime</th><th>Description</th><th>When New Instance Created</th><th>Best For</th><th>Example</th></tr>
<tr>
    <td><strong>Transient</strong></td>
    <td>New instance every time it's injected</td>
    <td><strong>Every single time</strong></td>
    <td>Lightweight, stateless services</td>
    <td><code>IEmailService</code>, <code>IValidator&lt;T&gt;</code></td>
</tr>
<tr>
    <td><strong>Scoped</strong></td>
    <td>One instance per HTTP request</td>
    <td><strong>Once per client request</strong></td>
    <td>DbContext, Repositories, user-specific data</td>
    <td><code>AppDbContext</code>, <code>IUserRepository</code></td>
</tr>
<tr>
    <td><strong>Singleton</strong></td>
    <td>One instance for the entire application lifetime</td>
    <td><strong>Only once</strong> (first request)</td>
    <td>Caching, Configuration, shared state</td>
    <td><code>IMemoryCache</code>, <code>IConfiguration</code></td>
</tr>
</table>

<pre><code>// SERVICES TO DEMONSTRATE LIFETIMES:
public interface IGuidService { Guid GetGuid(); }

// TRANSIENT: Different GUID every time
public class TransientGuid : IGuidService
{
    private readonly Guid _guid = Guid.NewGuid();
    public Guid GetGuid() =&gt; _guid;  // Different every call!
}

// SCOPED: Same GUID within one HTTP request
public class ScopedGuid : IGuidService
{
    private readonly Guid _guid = Guid.NewGuid();
    public Guid GetGuid() =&gt; _guid;  // Same within request, different across requests
}

// SINGLETON: Same GUID forever (until app restarts)
public class SingletonGuid : IGuidService
{
    private readonly Guid _guid = Guid.NewGuid();
    public Guid GetGuid() =&gt; _guid;  // Always identical!
}


// REGISTRATION in Program.cs:
builder.Services.AddTransient&lt;IGuidService, TransientGuid&gt;();
builder.Services.AddScoped&lt;IGuidService, ScopedGuid&gt;();        // ← DbContext goes here!
builder.Services.AddSingleton&lt;IGuidService, SingletonGuid&gt;();   // ← Cache goes here!

// Also common registrations:
builder.Services.AddScoped&lt;AppDbContext&gt;();                     // DB Context = Scoped
builder.Services.AddSingleton&lt;IMemoryCache, MemoryCache&gt;();     // Cache = Singleton


// CONTROLLER demonstrating injection:
[ApiController]
[Route("api/[controller]")]
public class DemoController : ControllerBase
{
    private readonly IGuidService _transient1;
    private readonly IGuidService _transient2;
    private readonly IGuidService _scoped1;
    private readonly IGuidService _scoped2;
    private readonly IGuidService _singleton1;
    private readonly IGuidService _singleton2;
    
    // Inject same service TWICE to see difference!
    public DemoController(
        IGuidService t1, IGuidService t2,
        IGuidService s1, IGuidService s2,
        IGuidService sg1, IGuidService sg2)
    {
        _transient1 = t1; _transient2 = t2;
        _scoped1 = s1; _scoped2 = s2;
        _singleton1 = sg1; _singleton2 = sg2;
    }
    
    [HttpGet]
    public IActionResult Get()
    {
        return Ok(new
        {
            Transient_Same = _transient1.GetGuid() == _transient2.GetGuid(),
            Scoped_Same = _scoped1.GetGuid() == _scoped2.GetGuid(),
            Singleton_Same = _singleton1.GetGuid() == _singleton2.GetGuid()
        });
    }
}
/* OUTPUT:
{
    "Transient_Same": false,    // Different instances!
    "Scoped_Same": true,        // Same within request
    "Singleton_Same": true      // Always same
}*/</code></pre>


<!-- TOPIC 23: MVC Pattern -->
<h3 id="topic23" class="page-break">23. MVC Pattern</h3>

<div class="diagram-box">Browser/Client
        │
        │ HTTP Request (GET /users)
        ▼
   ┌─────────────┐
   │ CONTROLLER  │  ◄── Receives request, decides what to do
   │             │      - Validates input parameters
   │             │      - Calls Model/Service layer
   │             │      - Selects appropriate View
   └──────┬──────┘
          │ returns Model data
          ▼
   ┌─────────────┐
   │    MODEL    │  ◄── Data + Business Logic
   │             │      - Entities/Domain classes
   │             │      - Database operations
   │             │      - Business rules/validation
   └──────┬──────┘
          │ passes data
          ▼
   ┌─────────────┐
   │    VIEW     │  ◄── Presentation Layer (UI)
   │             │      - HTML template (.cshtml)
   │             │      - Displays data from Model
   │             │      - User interaction elements
   └──────┬──────┘
          │
          │ HTML Response
          ▼
   Browser/Client (renders HTML page)</div>

<pre><code>// ==================== MODEL ====================
// Represents data and business rules
public class UserViewModel
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Email { get; set; }
    public DateTime JoinDate { get; set; }
}

// ==================== CONTROLLER ====================
// Handles incoming HTTP requests, coordinates between Model and View
public class UserController : Controller
{
    private readonly IUserService _userService;
    
    public UserController(IUserService userService)
    {
        _userService = userService;
    }
    
    // ACTION: Handles GET /User/Index
    public IActionResult Index()
    {
        // 1. Get data from Model/Service layer
        var users = _userService.GetAllActiveUsers();
        
        // 2. Transform to ViewModel (DTO pattern)
        var viewModels = users.Select(u =&gt; new UserViewModel
        {
            Id = u.Id,
            Name = u.FullName,
            Email = u.Email,
            JoinDate = u.CreatedAt
        });
        
        // 3. Pass to View for rendering
        return View(viewModels);
    }
    
    // ACTION: Handles GET /User/Details/5
    public IActionResult Details(int id)
    {
        var user = _userService.GetById(id);
        if (user == null) return NotFound();
        return View(user);
    }
}

// ==================== VIEW ====================
// Razor template file (Index.cshtml)
@model IEnumerable&lt;UserViewModel&gt;

@{
    ViewData["Title"] = "User Management";
}

&lt;h1&gt;User List&lt;/h1&gt;

&lt;table class="table"&gt;
    &lt;thead&gt;
        &lt;tr&gt;
            &lt;th&gt;Name&lt;/th&gt;
            &lt;th&gt;Email&lt;/th&gt;
            &lt;th&gt;Join Date&lt;/th&gt;
            &lt;th&gt;Actions&lt;/th&gt;
        &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
        @foreach (var user in Model)
        {
            &lt;tr&gt;
                &lt;td&gt;@user.Name&lt;/td&gt;
                &lt;td&gt;@user.Email&lt;/td&gt;
                &lt;td&gt;@user.JoinDate.ToShortDateString()&lt;/td&gt;
                &lt;td&gt;
                    &lt;a asp-action="Details" asp-route-id="@user.Id"&gt;View&lt;/a&gt;
                    &lt;a asp-action="Edit" asp-route-id="@user.Id"&gt;Edit&lt;/a&gt;
                &lt;/td&gt;
            &lt;/tr&gt;
        }
    &lt;/tbody&gt;
&lt;/table&gt;</code></pre>


<!-- TOPIC 24: HTTP Methods -->
<h3 id="topic24" class="page-break">24. HTTP Methods: POST, GET, PUT, DELETE</h3>

<table>
<tr><th>Method</th><th>Purpose</th><th>Idempotent?*</th><th>Safe?**</th><th>Request Body</th><th>Typical Response</th></tr>
<tr>
    <td><strong>GET</strong></td>
    <td>Retrieve/Read resource(s)</td>
    <td>✔️ Yes</td>
    <td>✔️ Yes</td>
    <td>No body</td>
    <td>200 OK + resource representation</td>
</tr>
<tr>
    <td><strong>POST</strong></td>
    <td>Create NEW resource</td>
    <td>❌ No</td>
    <td>❌ No</td>
    <td>Resource data (JSON/XML)</td>
    <td>201 Created + Location header</td>
</tr>
<tr>
    <td><strong>PUT</strong></td>
    <td>Replace/update ENTIRE resource</td>
    <td>✔️ Yes</td>
    <td>❌ No</td>
    <td>Complete resource data</td>
    <td>204 No Content (or 200)</td>
</tr>
<tr>
    <td><strong>PATCH</strong></td>
    <td>PARTIAL update (specific fields)</td>
    <td>❌ No</td>
    <td>❌ No</td>
    <td>Patch document (JSON Patch)</td>
    <td>204 No Content (or 200)</td>
</tr>
<tr>
    <td><strong>DELETE</strong></td>
    <td>Remove resource</td>
    <td>✔️ Yes</td>
    <td>❌ No</td>
    <td>No body usually</td>
    <td>204 No Content (or 200)</td>
</tr>
</table>
<p style="font-size:0.9em;color:#666;">*Idempotent: Calling multiple times = same result as calling once | **Safe: Does not modify server state</p>

<pre><code>[ApiController]
[Route("api/[controller]")]
public class ProductsController : ControllerBase
{
    private readonly IProductService _service;
    
    public ProductsController(IProductService service) =&gt; _service = service;
    
    // ============ GET: Read ============
    // GET /api/products
    // GET /api/products?page=1&amp;size=10
    [HttpGet]
    public async Task&lt;ActionResult&lt;IEnumerable&lt;ProductDto&gt;&gt; GetAll(
        [FromQuery] int page = 1, [FromQuery] int size = 10)
    {
        var result = await _service.GetAllAsync(page, size);
        return Ok(result);
    }
    
    // GET /api/products/5
    [HttpGet("{id}")]
    public async Task&lt;ActionResult&lt;ProductDto&gt;&gt; GetById(int id)
    {
        var product = await _service.GetByIdAsync(id);
        if (product == null) return NotFound(new { message = "Not found" });
        return Ok(product);
    }
    
    // ============ POST: Create ============
    // POST /api/products
    // Body: { "name": "Laptop", "price": 999.99 }
    [HttpPost]
    public async Task&lt;ActionResult&lt;ProductDto&gt;&gt; Create([FromBody] CreateProductDto dto)
    {
        if (!ModelState.IsValid) return BadRequest(ModelState);
        
        var created = await _service.CreateAsync(dto);
        
        // Return 201 Created with Location header pointing to new resource
        return CreatedAtAction(nameof(GetById), new { id = created.Id }, created);
    }
    
    // ============ PUT: Full Update ============
    // PUT /api/products/5
    [HttpPut("{id}")]
    public async Task&lt;IActionResult&gt; Update(int id, [FromBody] UpdateProductDto dto)
    {
        if (id != dto.Id) return BadRequest("ID mismatch");
        
        var exists = await _service.ExistsAsync(id);
        if (!exists) return NotFound();
        
        await _service.UpdateAsync(dto);
        return NoContent(); // 204 Success, no response body
    }
    
    // ============ DELETE: Remove ============
    // DELETE /api/products/5
    [HttpDelete("{id}")]
    public async Task&lt;IActionResult&gt; Delete(int id)
    {
        var exists = await _service.ExistsAsync(id);
        if (!exists) return NotFound();
        
        await _service.DeleteAsync(id);
        return NoContent(); // 204 Success
    }
}</code></pre>

<table>
<tr><th>Status Code</th><th>Meaning</th><th>When to Use</th></tr>
<tr><td><strong>200 OK</strong></td><td>Request succeeded</td><td>Successful GET, PUT, PATCH with response body</td></tr>
<tr><td><strong>201 Created</strong></td><td>Resource successfully created</td><td>Successful POST (include Location header)</td></tr>
<tr><td><strong>204 No Content</strong></td><td>Success but no response body</td><td>Successful DELETE, PUT (nothing to return)</td></tr>
<tr><td><strong>400 Bad Request</strong></td><td>Invalid request syntax/data</td><td>Validation failed, malformed JSON</td></tr>
<tr><td><strong>401 Unauthorized</strong></td><td>Authentication required/failed</td><td>Missing or invalid token</td></tr>
<tr><td><strong>403 Forbidden</strong></td><td>Authenticated but not authorized</td><td>User lacks permission for resource</td></tr>
<tr><td><strong>404 Not Found</strong></td><td>Resource doesn't exist</td><td>ID not found in database</td></tr>
<tr><td><strong>500 Server Error</strong></td><td>Internal server error</td><td>Unhandled exception, bug</td></tr>
</table>


<!-- TOPIC 25: JWT Token -->
<h3 id="topic25" class="page-break">25. JWT Token (JSON Web Token)</h3>

<div class="definition-box">
<strong>Definition:</strong> JWT is a compact, URL-safe token format used to securely transmit information between parties as a JSON object. It consists of three parts separated by dots: Header.Payload.Signature.
</div>

<div class="diagram-box">JWT TOKEN STRUCTURE:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkw
└──────────────────────────────┘└──────────────────────────────────────┘
         HEADER                            PAYLOAD
{"alg":"HS256","typ":"JWT"}     {"userId":1,"role":"admin","exp":...}

.FlMxW7y2bG3vK9pQmNjRsTuVwXyZ
└──────────────────────────────────────────────────────────────┘
                         SIGNATURE
HMACSHA256(base64url(header) + "." + base64url(payload), secret-key)

FORMAT: Header.Payload.Signature</div>

<pre><code>// ==================== JWT SERVICE ====================
public class JwtTokenService
{
    private readonly string _secretKey;
    private readonly string _issuer;
    private readonly string _audience;
    private readonly int _expirationMinutes;
    
    public JwtTokenService(IConfiguration config)
    {
        _secretKey = config["Jwt:SecretKey"] ?? throw new Exception("Missing JWT secret");
        _issuer = config["Jwt:Issuer"] ?? "myapp.com";
        _audience = config["Jwt:Audience"] ?? "myapp.com";
        _expirationMinutes = int.Parse(config["Jwt:ExpirationMinutes"] ?? "60");
    }
    
    // GENERATE TOKEN for authenticated user
    public string GenerateToken(User user, IList&lt;string&gt; roles)
    {
        var securityKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(_secretKey));
        var credentials = new SigningCredentials(securityKey, SecurityAlgorithms.HmacSha256);
        
        // Claims: Information stored INSIDE the token
        var claims = new List&lt;Claim&gt;
        {
            new Claim(ClaimTypes.NameIdentifier, user.Id.ToString()),
            new Claim(ClaimTypes.Email, user.Email),
            new Claim(ClaimTypes.Name, user.UserName),
            new Claim(JwtRegisteredClaimNames.Jti, Guid.NewGuid().ToString()) // Unique token ID
        };
        
        // Add roles as claims (for authorization)
        foreach (var role in roles)
        {
            claims.Add(new Claim(ClaimTypes.Role, role));
        }
        
        var token = new JwtSecurityToken(
            issuer: _issuer,
            audience: _audience,
            claims: claims,
            expires: DateTime.Now.AddMinutes(_expirationMinutes),
            signingCredentials: credentials
        );
        
        return new JwtSecurityTokenHandler().WriteToken(token);
    }
}


// ==================== AUTH CONTROLLER ====================
[ApiController]
[Route("api/[controller]")]
public class AuthController : ControllerBase
{
    private readonly JwtTokenService _jwtService;
    private readonly UserManager&lt;User&gt; _userManager;
    
    public AuthController(JwtTokenService jwtService, UserManager&lt;User&gt; userManager)
    {
        _jwtService = jwtService;
        _userManager = userManager;
    }
    
    // LOGIN - Issues JWT token upon successful authentication
    [HttpPost("login")]
    public async Task&lt;ActionResult&lt;AuthResponse&gt;&gt; Login([FromBody] LoginRequest request)
    {
        // 1. Find user by email
        var user = await _userManager.FindByEmailAsync(request.Email);
        if (user == null || !await _userManager.CheckPasswordAsync(user, request.Password))
        {
            return Unauthorized(new { message = "Invalid email or password" });
        }
        
        // 2. Check if email is confirmed
        if (!await _userManager.IsEmailConfirmedAsync(user))
        {
            return BadRequest(new { message = "Please confirm your email address" });
        }
        
        // 3. Get user roles
        var roles = await _userManager.GetRolesAsync(user);
        
        // 4. Generate and return JWT token
        var token = _jwtService.GenerateToken(user, roles);
        
        return Ok(new AuthResponse
        {
            Token = token,
            ExpiresIn = _expirationMinutes,
            User = new UserInfoDto
            {
                Id = user.Id,
                Email = user.Email,
                UserName = user.UserName,
                Roles = roles
            }
        });
    }
}


// ==================== PROTECTED ENDPOINT ====================
[ApiController]
[Route("api/[controller]")]
[Authorize] // ← Requires valid JWT token in Authorization header!
public class ProfileController : ControllerBase
{
    [HttpGet]
    public ActionResult&lt;MyProfileResponse&gt; GetMyProfile()
    {
        // Extract info from token claims (set automatically by framework)
        var userId = User.FindFirstValue(ClaimTypes.NameIdentifier);
        var userEmail = User.FindFirstValue(ClaimTypes.Email);
        var userRoles = User.FindAll(ClaimTypes.Role).Select(c =&gt; c.Value);
        
        return Ok(new MyProfileResponse
        {
            Id = userId,
            Email = userEmail,
            Roles = userRoles
        });
    }
    
    [HttpGet("admin-data")]
    [Authorize(Roles = "Admin")] // ← Requires Admin role specifically!
    public ActionResult&lt;object&gt; GetAdminData()
    {
        return Ok(new { secretData = "Only administrators can see this!" });
    }
}

/*
appsettings.json configuration:
{
  "Jwt": {
    "SecretKey": "YourSuperSecretKeyThatIsAtLeast32CharactersLong!",
    "Issuer": "myapp.com",
    "Audience": "myapp.com",
    "ExpirationMinutes": "60"
  }
}
*/</code></pre>

<div class="info-box">
<span class="box-title">How clients send JWT tokens:</span>
In the HTTP Authorization header:<br>
<code>Authorization: Bearer eyJhbGciOiJIUzI1NiIs...</code>
</div>


<!-- TOPIC 26: CORS -->
<h3 id="topic26" class="page-break">26. CORS (Cross-Origin Resource Sharing)</h3>

<div class="definition-box">
<strong>The Problem:</strong> Browsers block web pages from making requests to a different domain (origin) than the one that served the web page. This is a security feature called <strong>Same-Origin Policy</strong>.
</div>

<div class="diagram-box">THE PROBLEM (Browser blocks cross-origin):
┌──────────────────┐              ┌──────────────────┐
│ Frontend (React) │              │ Backend (ASP.NET) │
│ localhost:3000   │  ──request──▶ │ localhost:5001    │
│                  │  ◀──BLOCKED!─ │                  │
│ Browser blocks it!              │                  │
└──────────────────┘              └──────────────────┘

THE SOLUTION (Configure CORS):
┌──────────────────┐              ┌──────────────────┐
│ Frontend (React) │              │ Backend (ASP.NET) │
│ localhost:3000   │  ──request──▶ │ localhost:5001    │
│                  │  ◀──200 OK── │                  │
│ Response received!              │ (CORS configured) │
└──────────────────┘              └──────────────────┘</div>

<pre><code>// Program.cs - Configure CORS policies
var builder = WebApplication.CreateBuilder(args);

// OPTION 1: Allow any origin (DEVELOPMENT ONLY!)
builder.Services.AddCors(options =&gt;
{
    options.AddPolicy("AllowAll", policy =&gt;
    {
        policy.AllowAnyOrigin()       // Any website can make requests
              .AllowAnyMethod()       // GET, POST, PUT, DELETE, etc.
              .AllowAnyHeader();      // Any headers (Content-Type, Auth, etc.)
    });
});

// OPTION 2: Specific origins (RECOMMENDED FOR PRODUCTION)
builder.Services.AddCors(options =&gt;
{
    options.AddPolicy("AllowSpecificOrigins", policy =&gt;
    {
        policy.WithOrigins(                    // Only these websites allowed:
                "https://www.myfrontend.com",
                "https://staging.myfrontend.com",
                "http://localhost:3000",       // Development environment
                "http://localhost:4200")       // Angular dev server
              .AllowAnyMethod()
              .AllowAnyHeader()
              .AllowCredentials();             // Allow cookies/auth tokens
    });
});

var app = builder.Build();

// IMPORTANT: Must be called BEFORE other middleware!
app.UseCors("AllowSpecificOrigins");

app.UseHttpsRedirection();
app.UseAuthentication();
app.UseAuthorization();
app.MapControllers();

app.Run();</code></pre>


<!-- TOPIC 27: Repository Pattern -->
<h3 id="topic27" class="page-break">27. Repository Pattern</h3>

<div class="definition-box">
<strong>Definition:</strong> An abstraction layer between business logic and data access code. It mediates between the domain and data mapping layers, providing a collection-like interface for accessing domain objects.
</div>

<pre><code>// ==================== 1. INTERFACE (The Contract) ====================
// Defines WHAT operations are available (not HOW they work)
public interface IUserRepository
{
    // CRUD Operations
    Task&lt;User?&gt; GetByIdAsync(int id);
    Task&lt;IEnumerable&lt;User&gt;&gt; GetAllAsync();
    Task&lt;IEnumerable&lt;User&gt;&gt; GetByRoleAsync(string role);
    Task&lt;User&gt; AddAsync(User entity);
    Task UpdateAsync(User entity);
    Task DeleteAsync(int id);
    
    // Utility
    Task&lt;bool&gt; ExistsAsync(int id);
    Task&lt;PagedResult&lt;User&gt;&gt; GetPagedAsync(int page, int size);
}


// ==================== 2. IMPLEMENTATION (The How) ====================
// Actual database operations using Entity Framework
public class UserRepository : IUserRepository
{
    private readonly AppDbContext _context;
    private readonly ILogger&lt;UserRepository&gt; _logger;
    
    public UserRepository(AppDbContext context, ILogger&lt;UserRepository&gt; logger)
    {
        _context = context;
        _logger = logger;
    }
    
    public async Task&lt;User?&gt; GetByIdAsync(int id)
    {
        _logger.LogInformation("Fetching user {UserId}", id);
        return await _context.Users.FindAsync(id);
    }
    
    public async Task&lt;IEnumerable&lt;User&gt;&gt; GetAllAsync()
    {
        return await _context.Users
            .OrderBy(u =&gt; u.Name)
            .AsNoTracking()  // Performance optimization for read-only
            .ToListAsync();
    }
    
    public async Task&lt;User&gt; AddAsync(User entity)
    {
        _logger.LogInformation("Creating user: {Email}", entity.Email);
        
        await _context.Users.AddAsync(entity);
        await _context.SaveChangesAsync();
        
        _logger.LogInformation("User created with ID: {UserId}", entity.Id);
        return entity;
    }
    
    public async Task DeleteAsync(int id)
    {
        var entity = await _context.Users.FindAsync(id) 
            ?? throw new NotFoundException($"User {id} not found");
        
        _context.Users.Remove(entity);
        await _context.SaveChangesAsync();
    }
    
    // ... other methods
}


// ==================== 3. REGISTRATION ====================
// Program.cs - Tell DI container which implementation to use
builder.Services.AddScoped&lt;IUserRepository, UserRepository&gt;();
// To switch to MongoDB: builder.Services.AddScoped&lt;IUserRepository, MongoUserRepository&gt;();


// ==================== 4. USAGE IN SERVICE LAYER ====================
public class UserService
{
    private readonly IUserRepository _repository;
    private readonly IEmailService _emailService;
    
    // Injected via constructor - doesn't know it's EF!
    public UserService(IUserRepository repository, IEmailService emailService)
    {
        _repository = repository;
        _emailService = emailService;
    }
    
    public async Task&lt;UserDto&gt; CreateUserAsync(CreateUserDto dto)
    {
        // Business rule: Check if email already exists
        if (await _repository.ExistsByEmail(dto.Email))
            throw new BusinessException("Email already registered");
        
        var user = new User
        {
            Name = dto.Name,
            Email = dto.Email.ToLower(),
            Role = "User"
        };
        
        // Delegate persistence to repository
        var created = await _repository.AddAsync(user);
        
        // Side effect via service
        await _emailService.SendWelcomeEmail(created.Email);
        
        return MapToDto(created);
    }
}</code></pre>

</div><!-- End Part 3 Container -->


<!-- ==================== PART 4: ADVANCED TOPICS ==================== -->
<div class="section-header page-break">
    <h2>PART 4: Advanced Topics</h2>
    <p>Architecture patterns, distributed systems, and enterprise design</p>
</div>

<div class="container">

<!-- TOPIC 28: Microservices -->
<h3 id="topic28">28. Microservices Architecture</h3>

<div class="definition-box">
<strong>Definition:</strong> An architectural approach where an application is composed of many small, independently deployable services organized around business capabilities. Each service runs in its own process and communicates via lightweight mechanisms (usually HTTP APIs or message queues).
</div>

<div class="comparison">
<div class="compare-col">
<h5>MONOLITHIC APPLICATION</h5>
<p>ONE BIG application containing everything</p>
<ul>
<li>Single codebase</li>
<li>Shared database</li>
<li>Deploy everything together</li>
<li>Tight coupling between modules</li>
</ul>
<p><strong>Deploy:</strong> Entire app for ANY change</p>
<p><strong>Scale:</strong> Scale entire app vertically</p>
</div>
<div class="compare-col good">
<h5>MICROSERVICES ARCHITECTURE</h5>
<p>Many SMALL independent services</p>
<ul>
<li>Separate codebases/repos</li>
<li>Own database per service</li>
<li>Independent deployment</li>
<li>Loose coupling via APIs/messages</li>
</ul>
<p><strong>Deploy:</strong> Only changed service</p>
<p><strong>Scale:</strong> Scale individual services</p>
</div>
</div>

<div class="diagram-box">MICROSERVICES ARCHITECTURE DIAGRAM:

┌────────────┐  ┌────────────┐  ┌────────────┐  ┌────────────┐
│   Auth     │  │   User     │  │   Order    │  │  Payment   │
│   Service   │  │   Service   │  │   Service   │  │   Service   │
│   :5001     │  │   :5002     │  │   :5003     │  │   :5004     │
└──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘
       │                │                │                │
       └────────────────┴────────────────┴────────────────┘
                        │
              ┌─────────▼─────────┐
              │   API GATEWAY     │  (:80 - Single entry point)
              │   (Kong/Nginx)    │
              └───────────────────┘

Each service has its OWN:
┌─────────────────────────────────┐
│  Order Service                   │
│  ─────────────────────────────── │
│  • Own Codebase (separate repo)  │
│  • Own Database (OrderDB)        │
│  • Own Deployment (Docker image) │
│  • Own Scaling (can have 3 inst.)│
│  • Own Team ownership            │
└─────────────────────────────────┘</div>

<table>
<tr><th>Microservices Pros ✅</th><th>Microservices Cons ❌</th></tr>
<tr><td>Independent deployment per service</td><td>Complex infrastructure (Kubernetes, Docker)</td></tr>
<tr><td>Technology diversity (Node, Python, C#, Go)</td><td>Network latency between services</td></tr>
<tr><td>Scalability per service (scale what needs it)</td><td>Distributed system complexity</td></tr>
<tr><td>Fault isolation (one down ≠ whole system)</td><td>Data consistency challenges (distributed transactions)</td></tr>
<tr><td>Team autonomy (own their services)</td><td>Testing complexity (integration testing)</td></tr>
<tr><td>Easier to understand small codebases</td><td>Operational overhead (monitoring, logging)</td></tr>
</table>


<!-- TOPIC 29: RabbitMQ -->
<h3 id="topic29" class="page-break">29. RabbitMQ (Message Broker)</h3>

<div class="definition-box">
<strong>Definition:</strong> RabbitMQ is a message broker that accepts, stores, and forwards messages between applications. It implements the Advanced Message Queuing Protocol (AMQP) and enables asynchronous, decoupled communication between services.
</div>

<table>
<tr><th>Scenario</th><th>Example</th></tr>
<tr><td><strong>Background tasks</strong></td><td>Send welcome email after user registration</td></tr>
<tr><td><strong>Decoupling services</strong></td><td>Order service publishes event, inventory/payment services subscribe</td></tr>
<tr><td><strong>Load balancing</strong></td><td>Distribute image processing among multiple worker servers</td></tr>
<tr><td><strong>Reliability</strong></td><td>Messages persisted until processed (won't lose them on failure)</td></tr>
<tr><td><strong>Rate limiting</strong></td><td>Queue up requests during traffic spikes</td></tr>
</table>

<pre><code>// ==================== DEFINE MESSAGE EVENT ====================
// Simple record representing a domain event
public record OrderCreatedEvent(
    Guid OrderId,
    string CustomerEmail,
    decimal TotalAmount,
    DateTime CreatedAt
);


// ==================== PRODUCER (Publisher) ====================
// Publishes events asynchronously (fire-and-forget)
public class OrderService
{
    private readonly IBus _bus;  // MassTransit IBus interface
    private readonly AppDbContext _dbContext;
    
    public OrderService(IBus bus, AppDbContext dbContext)
    {
        _bus = bus;
        _dbContext = dbContext;
    }
    
    public async Task&lt;Order&gt; PlaceOrderAsync(CreateOrderDto dto)
    {
        // 1. Persist order to database
        var order = new Order
        {
            Id = Guid.NewGuid(),
            CustomerEmail = dto.CustomerEmail,
            Items = dto.Items.Select(i =&gt; new OrderItem {...}).ToList(),
            TotalAmount = dto.TotalAmount,
            Status = "Created",
            CreatedAt = DateTime.UtcNow
        };
        
        _dbContext.Orders.Add(order);
        await _dbContext.SaveChangesAsync();
        
        // 2. PUBLISH event (async - fire and forget!)
        // Control returns IMMEDIATELY - doesn't wait for consumers!
        await _bus.Publish(new OrderCreatedEvent(
            order.Id,
            order.CustomerEmail,
            order.TotalAmount,
            order.CreatedAt
        ));
        
        return order;  // Returns to caller immediately
    }
}


// ==================== CONSUMER (Subscriber) ====================
// Listens for and processes events
public class OrderCreatedEmailConsumer : IConsumer&lt;OrderCreatedEvent&gt;
{
    private readonly IEmailService _emailService;
    private readonly ILogger&lt;OrderCreatedEmailConsumer&gt; _logger;
    
    public OrderCreatedEmailConsumer(
        IEmailService emailService, 
        ILogger&lt;OrderCreatedEmailConsumer&gt; logger)
    {
        _emailService = emailService;
        _logger = logger;
    }
    
    // This method is called automatically when a message arrives
    public async Task Consume(ConsumeContext&lt;OrderCreatedEvent&gt; context)
    {
        var eventMessage = context.Message;
        
        _logger.LogInformation("Processing order {OrderId}", eventMessage.OrderId);
        
        try
        {
            // Simulate slow operation (email sending)
            await _emailService.SendAsync(
                eventMessage.CustomerEmail,
                "Order Confirmation",
                $"Thank you! Your order {eventMessage.OrderId} of ${eventMessage.TotalAmount} received."
            );
            
            _logger.LogInformation("Email sent for order {OrderId}", eventMessage.OrderId);
        }
        catch (Exception ex)
        {
            _logger.LogError(ex, "Failed sending email for order {OrderId}", eventMessage.OrderId);
            throw; // Triggers retry mechanism or dead-letter queue
        }
    }
}


// ==================== REGISTRATION (Program.cs) ====================
builder.Services.AddMassTransit(x =&gt;
{
    x.AddConsumer&lt;OrderCreatedEmailConsumer&gt;();
    
    x.UsingRabbitMq((context, cfg) =&gt;
    {
        cfg.Host("localhost", "/", h =&gt;
        {
            h.Username("guest");
            h.Password("guest");
        });
        
        cfg.ReceiveEndpoint("order-created-email-queue", e =&gt;
        {
            e.ConfigureConsumer&lt;OrderCreatedEmailConsumer&gt;(context);
        });
    });
});</code></pre>


<!-- TOPIC 30: DDD Value Objects -->
<h3 id="topic30" class="page-break">30. DDD (Domain-Driven Design) - Value Objects</h3>

<table>
<tr><th>Aspect</th><th>Entity</th><th>Value Object</th></tr>
<tr><td><strong>Identity</strong></td>
    <td>Has unique identity (<code>Id</code>)</td>
    <td>Identified by its <strong>values</strong> (all properties)</td>
</tr>
<tr><td><strong>Equality</strong></td>
    <td>Same ID = Same object</td>
    <td>All properties equal = Same object</td>
</tr>
<tr><td><strong>Mutability</strong></td>
    <td>Can change state over time</td>
    <td><strong>Immutable</strong> (cannot change after creation)</td>
</tr>
<tr><td><strong>Examples</strong></td>
    <td>User, Order, Product, Employee</td>
    <td>Money, Address, DateRange, Color, Coordinates</td>
</tr>
<tr><td><strong>Lifecycle</strong></td>
    <td>Has continuous identity through changes</td>
    <td>Can be replaced entirely with new instance</td>
</tr>
</table>

<pre><code>// ==================== VALUE OBJECT: Money ====================
// Immutable - once created, values cannot change
public sealed class Money : IEquatable&lt;Money&gt;
{
    public decimal Amount { get; }
    public string Currency { get; }
    
    // Private constructor - forces use of factory methods
    private Money(decimal amount, string currency)
    {
        if (amount &lt; 0)
            throw new ArgumentException("Amount cannot be negative");
        if (string.IsNullOrWhiteSpace(currency))
            throw new ArgumentException("Currency is required");
            
        Amount = amount;
        Currency = currency.ToUpperInvariant();
    }
    
    // Factory methods (preferred over direct construction)
    public static Money FromDecimal(decimal amount, string currency)
        =&gt; new Money(amount, currency);
        
    public static Money Usd(decimal amount) =&gt; new Money(amount, "USD");
    public static Money Eur(decimal amount) =&gt; new Money(amount, "EUR");
    
    // Operations return NEW instances (immutability pattern!)
    public Money Add(Money other)
    {
        if (Currency != other.Currency)
            throw new InvalidOperationException("Cannot add different currencies");
        return new Money(Amount + other.Amount, Currency);
    }
    
    public Money Multiply(decimal factor)
        =&gt; new Money(Amount * factor, Currency);
    
    // Equality based on VALUES (not reference/memory address)
    public bool Equals(Money? other)
    {
        if (other is null) return false;
        return Amount == other.Amount &amp;&amp; Currency == other.Currency;
    }
    
    public override bool Equals(object? obj) =&gt; Equals(obj as Money);
    public override int GetHashCode() =&gt; HashCode.Combine(Amount, Currency);
    
    public override string ToString() =&gt; $"{Amount:N2} {Currency}";
}


// ==================== USING VALUE OBJECTS ====================
public class Order
{
    public Guid Id { get; }
    public Money Total { get; private set; }  // Value Object
    public Address ShippingAddress { get; }   // Another Value Object
    
    public Order(Guid id, Money total, Address shippingAddress)
    {
        Id = id;
        Total = total;
        ShippingAddress = shippingAddress;
    }
    
    public void AddItem(Money itemPrice)
    {
        // Creates NEW Money instance (immutable!)
        Total = Total.Add(itemPrice);
    }
}

// USAGE:
var price1 = Money.FromDecimal(29.99m, "USD");
var price2 = Money.Usd(49.99m);

var total = price1.Add(price2);  // Money(79.98, USD)
var discounted = total.Multiply(0.9m);  // Money(71.98, USD)

// Value objects are EQUAL by their values:
Console.WriteLine(price1.Equals(Money.FromDecimal(29.99m, "USD")));  // True
Console.WriteLine(price1 == price2);  // False (different amounts)</code></pre>


<!-- TOPIC 31: Caching -->
<h3 id="topic31" class="page-break">31. Caching Strategies</h3>

<table>
<tr><th>Aspect</th><th>In-Memory Cache</th><th>Distributed Cache (Redis)</th></tr>
<tr><td><strong>Storage location</strong></td>
    <td>Server's RAM (per server)</td>
    <td>External Redis server (shared)</td>
</tr>
<tr><td><strong>Sharing</strong></td>
    <td>NOT shared (each server has own cache)</td>
    <td>SHARED (all servers access same cache)</td>
</tr>
<tr><td><strong>Speed</strong></td>
    <td><strong>Fastest</strong> (direct RAM access)</td>
    <td>Fast (network hop + RAM)</td>
</tr>
<tr><td><strong>Capacity</strong></td>
    <td>Limited by server memory</td>
    <td>Very large (Redis cluster)</td>
</tr>
<tr><td><strong>Persistence</strong></td>
    <td>Lost on server restart</td>
    <td>Configurable persistence</td>
</tr>
<tr><td><strong>Best for</strong></td>
    <td>Single-server apps, session data</td>
    <td>Multi-server, microservices, shared data</td>
</tr>
</table>

<pre><code>// ==================== IN-MEMORY CACHE ====================
// Program.cs
builder.Services.AddMemoryCache(options =&gt;
{
    options.SizeLimit = 1024; // Optional: limit cache size in MB
});

// Cached Service Implementation
public class CachedProductService
{
    private readonly IMemoryCache _cache;
    private readonly ProductRepository _repository;
    
    public CachedProductService(IMemoryCache cache, ProductRepository repo)
    {
        _cache = cache;
        _repository = repo;
    }
    
    public async Task&lt;Product?&gt; GetByIdAsync(int id)
    {
        string cacheKey = $"product_{id}";
        
        // Try to get from cache first
        if (_cache.TryGetValue(cacheKey, out Product? cachedProduct))
        {
            return cachedProduct;  // Cache HIT! Fast return
        }
        
        // Cache MISS - fetch from database
        var product = await _repository.GetByIdAsync(id);
        
        if (product != null)
        {
            // Store in cache with expiration policy
            var options = new MemoryCacheEntryOptions
            {
                AbsoluteExpirationRelativeToNow = TimeSpan.FromMinutes(30),
                Priority = CacheItemPriority.Normal,
                
                // Eviction callback (optional - for monitoring)
                Size = 1
            };
            
            options.RegisterPostEvictionCallback((key, value, reason, state) =&gt;
            {
                Console.WriteLine($"Cache entry {key} evicted: {reason}");
            });
            
            _cache.Set(cacheKey, product, options);
        }
        
        return product;
    }
    
    // Invalidate (remove) cache when data changes
    public void InvalidateProduct(int id)
    {
        _cache.Remove($"product_{id}");
    }
}


// ==================== DISTRIBUTED CACHE (REDIS) ====================
// Program.cs
builder.Services.AddStackExchangeRedisCache(options =&gt;
{
    options.Configuration = "localhost:6379";
    options.InstanceName = "MyApp_";  // Prefix for all keys
});

// Redis Cache Service (similar interface!)
public class RedisCachedService
{
    private readonly IDistributedCache _cache;
    
    public RedisCachedService(IDistributedCache cache) =&gt; _cache = cache;
    
    public async Task&lt;string?&gt; GetStringAsync(string key)
        =&gt; await _cache.GetStringAsync(key);
    
    public async Task SetStringAsync(string key, string value, TimeSpan expiry)
    {
        var options = new DistributedCacheEntryOptions
        {
            AbsoluteExpirationRelativeToNow = expiry
        };
        await _cache.SetStringAsync(key, value, options);
    }
    
    // Note: Distributed cache stores bytes/strings, so serialize/deserialize objects
    public async Task&lt;T?&gt; GetAsync&lt;T&gt;(string key) where T : class
    {
        var json = await _cache.GetStringAsync(key);
        return string.IsNullOrEmpty(json) ? null : JsonSerializer.Deserialize&lt;T&gt;(json);
    }
    
    public async Task SetAsync&lt;T&gt;(string key, T value, TimeSpan expiry) where T : class
    {
        var json = JsonSerializer.Serialize(value);
        var options = new DistributedCacheEntryOptions
        {
            AbsoluteExpirationRelativeToNow = expiry
        };
        await _cache.SetStringAsync(key, json, options);
    }
}</code></pre>


<!-- TOPIC 32: Clean Architecture -->
<h3 id="topic32" class="page-break">32. Clean Architecture</h3>

<div class="diagram-box">CLEAN ARCHITECTURE LAYERS (from innermost to outermost):

 ┌─────────────────────────────────────────────────────────────────┐
 │                    PRESENTATION LAYER (Outermost)               │
 │  • Controllers (Web API)                                        │
 │  • DTOs (Data Transfer Objects)                                 │
 │  • Program.cs (Composition Root / DI Setup)                    │
 │  • Middlewares                                                  │
 └──────────────────────────────┬──────────────────────────────────┘
                                 │ Depends on
 ┌──────────────────────────────▼──────────────────────────────────┐
 │                    APPLICATION LAYER                             │
 │  • Interfaces (IRepository, IService)                           │
 │  • Services / Use Cases                                         │
 │  • DTOs (mapping between layers)                                │
 │  • Validators                                                   │
 │  • AutoMapper Profiles                                          │
 └──────────────────────────────┬──────────────────────────────────┘
                                 │ Depends on
 ┌──────────────────────────────▼──────────────────────────────────┐
 │                      DOMAIN LAYER (Innermost)                    │
 │  • Entities (with identity)                                     │
 │  • Value Objects                                                │
 │  • Domain Events                                                │
 │  • Repository Interfaces (contracts only)                       │
 │  • Domain Services (pure business logic)                        │
 │                                                                  │
 │  ⚠️ ZERO dependencies on: EF, ASP.NET, JSON, File I/O, etc.   │
 └──────────────────────────────┬──────────────────────────────────┘
                                 │ Implements
 ┌──────────────────────────────▼──────────────────────────────────┐
 │                   INFRASTRUCTURE LAYER                            │
 │  • Entity Framework (DbContext, Repositories)                   │
 │  • External APIs (HttpClient wrappers)                           │
 │  • File Storage (Azure Blob, Local filesystem)                   │
 │  • Email Services (SMTP, SendGrid)                               │
 │  • Caching (Redis, Memory)                                       │
 └─────────────────────────────────────────────────────────────────┘

 CRITICAL RULE: Dependencies ALWAYS point INWARD →
 Inner layers NEVER depend on outer layers!</div>

<pre><code>// Sample DOMAIN Entity (Pure C#, NO EF dependencies!)
namespace MyProject.Domain.Entities;

public class Order
{
    // Private setter - protect invariants
    public Guid Id { get; private set; }
    public Guid CustomerId { get; private set; }
    private readonly List&lt;OrderItem&gt; _items = new();
    public IReadOnlyCollection&lt;OrderItem&gt; Items =&gt; _items.AsReadOnly();
    public OrderStatus Status { get; private set; }
    public DateTime CreatedAt { get; private set; }
    public Money TotalAmount { get; private set; }
    
    // Protected constructor (force use of factory method)
    protected Order() { }
    
    // Factory method - enforces business rules at creation
    public static Order Create(Guid customerId, Money initialAmount)
    {
        if (customerId == Guid.Empty)
            throw new DomainException("Customer ID is required");
            
        return new Order
        {
            Id = Guid.NewGuid(),
            CustomerId = customerId,
            Status = OrderStatus.Pending,
            CreatedAt = DateTime.UtcNow,
            TotalAmount = initialAmount
        };
    }
    
    // Behavior methods (NOT just property setters!)
    public void AddItem(OrderItem item)
    {
        if (Status != OrderStatus.Pending)
            throw new DomainException("Cannot add items to non-pending order");
            
        _items.Add(item);
        RecalculateTotal();
    }
    
    public void Confirm()
    {
        if (!_items.Any())
            throw new DomainException("Cannot confirm empty order");
        Status = OrderStatus.Confirmed;
    }
    
    private void RecalculateTotal()
    {
        TotalAmount = Money.Usd(_items.Sum(i =&gt; i.LineTotal.Amount));
    }
}</code></pre>


<!-- TOPIC 33: API Versioning -->
<h3 id="topic33" class="page-break">33. API Versioning</h3>

<div class="info-box">
<span class="box-title">Why Version APIs?</span>
<ul>
    <li><strong>Breaking changes:</strong> Changing response structure, removing fields, renaming properties</li>
    <li><strong>Backward compatibility:</strong> Old mobile apps keep working while you improve the API</li>
    <li><strong>Gradual migration:</strong> Clients upgrade to newer versions at their own pace</li>
    <li><strong>Parallel development:</strong> Multiple versions coexist during transition periods</li>
</ul>
</div>

<pre><code>// Program.cs - Configure API Versioning
builder.Services.AddApiVersioning(options =&gt;
{
    // Default version if client doesn't specify
    options.DefaultApiVersion = new ApiVersion(1, 0);
    
    // Report versions in response headers (helpful for clients)
    options.ReportApiVersions = true;
    
    // Assume version 1.0 if not specified (client-friendly)
    options.AssumeDefaultVersionWhenUnspecified = true;
    
    // How clients specify which version they want:
    options.ApiVersionReader = ApiVersionReader.Combine(
        new UrlSegmentApiVersionReader(),      // /api/v1/users
        new HeaderApiVersionReader("X-API-Version", "Api-Version"),
        new QueryStringApiVersionReader("api-version")  // ?api-version=1
    );
});


// ===== VERSION 1 CONTROLLER (Legacy) =====
[ApiVersion("1.0")]
[Deprecated] // Mark old version as deprecated
[Route("api/v{version:apiVersion}/[controller]")]
public class UsersControllerV1 : ControllerBase
{
    [HttpGet]
    public ActionResult&lt;IEnumerable&lt;UserDtoV1&gt;&gt; Get()
    {
        // Old structure - fewer fields
        var users = _service.GetAll();
        return Ok(users.Select(u =&gt; new UserDtoV1
        {
            Id = u.Id,
            Name = u.Name,
            Email = u.Email
            // No phone, no avatar, no last login date
        }));
    }
}


// ===== VERSION 2 CONTROLLER (Current) =====
[ApiVersion("2.0")]
[Route("api/v{version:apiVersion}/[controller]")]
public class UsersControllerV2 : ControllerBase
{
    [HttpGet]
    public ActionResult&lt;PagedResponse&lt;UserDtoV2&gt;&gt; Get([FromQuery] PaginationParams paging)
    {
        // New structure - more fields, pagination, better performance
        var result = _service.GetPaged(paging.Page, paging.Size);
        return Ok(new PagedResponse&lt;UserDtoV2&gt;
        {
            Data = result.Items.Select(u =&gt; new UserDtoV2
            {
                Id = u.Id,
                Name = u.Name,
                Email = u.Email,
                PhoneNumber = u.Phone,        // NEW field
                AvatarUrl = u.AvatarUrl,       // NEW field
                LastLoginAt = u.LastLoginAt,   // NEW field
                Roles = u.Roles                // NEW field
            }),
            Page = result.Page,
            PageSize = result.Size,
            TotalCount = result.TotalCount,
            HasNext = result.HasNextPage
        });
    }
}

/* CLIENT REQUESTS:

Version 1:
GET /api/v1/users
Or: GET /api/users?api-version=1
Or with header: X-API-Version: 1

Version 2:
GET /api/v2/users?page=1&amp;size=20
Or: GET /api/users?api-version=2&amp;page=1&amp;size=20

RESPONSE HEADERS (when ReportApiVersions = true):
api-supported-versions: 1.0, 2.0
api-deprecated-versions: 1.0
*/</code></pre>

</div><!-- End Part 4 Container -->


<!-- ==================== CHEAT SHEET ==================== -->
<div class="section-header page-break">
    <h2>⭐ Quick Reference Cheat Sheet</h2>
    <p>Top interview questions - one-line answers for quick review</p>
</div>

<div class="container">

<h3 id="cheatsheet">Essential Interview Questions - At a Glance</h3>

<table class="cheat-sheet-table">
<tr><th>#</th><th>Question</th><th>Quick Answer</th></tr>
<tr><td>1</td><td><strong>Abstract vs Interface</strong></td><td>Abstract: has code + single inheritance | Interface: pure contract + multiple inheritance</td></tr>
<tr><td>2</td><td><strong>Override vs Overload</strong></td><td>Override: re-implement parent's virtual method (runtime polymorphism) | Overload: same name, different params (compile-time)</td></tr>
<tr><td>3</td><td><strong>Virtual vs Abstract</strong></td><td>Virtual: has body, optional override | Abstract: no body, mandatory override</td></tr>
<tr><td>4</td><td><strong>DI Lifetimes</strong></td><td>Transient: new每次 | Scoped: once per HTTP request | Singleton: once for entire app lifetime</td></tr>
<tr><td>5</td><td><strong>First vs FirstOrDefault</strong></td><td>First: throws InvalidOperationException if not found | FirstOrDefault: returns null/default if not found</td></tr>
<tr><td>6</td><td><strong>Lazy vs Eager Loading</strong></td><td>Lazy: loads on access via virtual proxy (risk of N+1) | Eager: loads with query via Include()</td></tr>
<tr><td>7</td><td><strong>Code First vs DB First</strong></td><td>Code First: write C# classes → generate database | DB First: design DB → scaffold C# classes</td></tr>
<tr><td>8</td><td><strong>Middleware vs Filter</strong></td><td>Middleware: global pipeline (all HTTP requests) | Filter: MVC action level only</td></tr>
<tr><td>9</td><td><strong>JWT Structure</strong></td><td>Header.Payload.Signature - Base64Url encoded, signed token for stateless auth</td></tr>
<tr><td>10</td><td><strong>Repository Pattern</strong></td><td>Abstraction layer between business logic and data access code</td></tr>
<tr><td>11</td><td><strong>SOLID Principles</strong></td><td>SRP, OCP, LSP, ISP, DIP - five design principles for maintainable software</td></tr>
<tr><td>12</td><td><strong>Value Object</strong></td><td>Immutable object identified by its values (not ID), e.g., Money, Address, DateRange</td></tr>
<tr><td>13</td><td><strong>Clean Architecture</strong></td><td>Domain → Application → Infrastructure → Presentation (dependencies inward)</td></tr>
<tr><td>14</td><td><strong>Microservices</strong></td><td>Small independent services communicating via HTTP APIs or message queues</td></tr>
<tr><td>15</td><td><strong>CORS</strong></td><td>Browser security feature; configure server to allow cross-origin requests</td></tr>
<tr><td>16</td><td><strong>SP vs Function</strong></td><td>SP: can modify data, flexible | Function: must return value, usable in SELECT</td></tr>
<tr><td>17</td><td><strong>Static class/member</strong></td><td>Shared among all instances, accessed via class name (not object instance)</td></tr>
<tr><td>18</td><td><strong>Sealed class</strong></td><td>Final class that cannot be inherited or extended further</td></tr>
<tr><td>19</td><td><strong>Encapsulation</strong></td><td>Hiding internal data, exposing controlled access via properties with validation</td></tr>
<tr><td>20</td><td><strong>Dependency Injection</strong></td><td>Providing dependencies via constructor injection instead of creating with `new` keyword</td></tr>
</table>

</div>


<!-- ==================== INTERVIEW TIPS ==================== -->
<div class="section-header page-break">
    <h2>💡 Interview Tips for Beginners</h2>
    <p>Strategies to succeed in your technical interview</p>
</div>

<div class="container">

<div class="comparison">
<div class="compare-col good">
<h5>✅ DO These Things</h5>
<ol>
<li><strong>Start simple</strong> - Give a brief answer first, then elaborate with details</li>
<li><strong>Give examples</strong> - Always say "In my project, I used..." to show practical experience</li>
<li><strong>Draw diagrams</strong> - Sketch architecture, flow charts, or data models when explaining</li>
<li><strong>Be honest</strong> - Say "I'm not sure about X, but I think..." rather than making things up</li>
<li><strong>Ask questions</strong> - Clarify ambiguous questions before answering</li>
<li><>Show enthusiasm</strong> - Demonstrate eagerness to learn and grow</li>
<li><strong>Think out loud</strong> - Verbalize your thought process during problem-solving</li>
</ol>
</div>
<div class="compare-col bad">
<h5>❌ DON'T Do These</h5>
<ol>
<li><strong>Don't memorize</strong> - Understand concepts deeply and explain in YOUR OWN words</li>
<li><strong>Don't give textbook definitions</strong> - Interviewers want understanding, not recitation</li>
<li><strong>Don't panic</strong> - Stay calm even if you don't know something</li>
<li><strong>Don't argue</strong> - Respectfully discuss, don't fight with the interviewer</li>
<li><strong>Don't badmouth</strong> - Never speak negatively about previous employers or projects</li>
<li><strong>Don't rush</strong> - Take time to think before answering complex questions</li>
<li><strong>Don't give up</strong> - If stuck, explain your thought process and ask for hints</li>
</ol>
</div>
</div>

<div class="info-box">
<span class="box-title">🎯 Common Follow-up Questions (Be Prepared!)</span>
<ul>
<li>"Why did you choose this approach over alternatives?"</li>
<li>"What are the trade-offs of this solution?"</li>
<li>"How would you test this code?"</li>
<li>"When would you NOT use this pattern/approach?"</li>
<li>"How would this scale to 1 million users?"</li>
<li>"What happens if this fails? How do you handle errors?"</li>
</ul>
</div>

<div class="success-box">
<span class="box-title">🏆 Final Reminder</span>
<p style="font-size:1.1em;margin:0;"><strong>Employers hire for potential and attitude, not just knowledge.</strong> Show them you're eager to learn, can communicate clearly, and work well in teams. Technical skills can be taught; the right mindset is invaluable!</p>
</div>

<div style="text-align:center; margin-top:50px; padding:30px; background:linear-gradient(135deg, #667eea 0%, #764ba2 100%); border-radius:16px; color:white;">
<h2 style="color:white; margin-bottom:10px;">🎉 Good Luck With Your Interview!</h2>
<p style="opacity:0.9;font-size:1.05em;">You've got this! Remember: preparation meets opportunity.</p>
<p style="margin-top:15px; opacity:0.8;font-size:0.95em;">Document prepared for .NET Developer Interview Preparation</p>
</div>

</div><!-- End Main Container -->

</body>
</html>
