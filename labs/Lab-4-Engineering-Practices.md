# Exercise 4 - Engineering Practices and Copilot Instructions

#### Duration: 55 minutes

## 🎯 Learning Objectives

By the end of this exercise, you will:
- Understand how to debug and inspect Copilot's decision-making process using the Debug Panel
- Configure personal instructions for consistent code generation across all your projects
- Create and manage repository-specific instructions for team standardization
- Monitor premium request usage to manage costs effectively
- Switch between AI models for different tasks and understand their strengths
- Master the custom instructions hierarchy (personal, repository, organization)
- Apply best practices for instruction file creation in real-world projects

## 📸 Scenario: Standardizing Development at PixelPerfect Gallery

Your team at PixelPerfect Gallery has been using GitHub Copilot for a few weeks now, and developers are getting great results. However, your manager has noticed some challenges:

- Different developers get varying code styles from Copilot for similar tasks
- Some developers get better results than others with similar prompts
- Team members aren't sure why Copilot makes certain suggestions
- The team needs to ensure consistent code patterns across the project
- Team members aren't sure which AI model to use for different scenarios

Today, you'll learn professional engineering practices for using GitHub Copilot effectively and explore instruction customization to:
- Understand AI decision-making through the Debug Panel
- Standardize code generation across the team with instruction files
- Optimize AI model usage for cost and efficiency
- Create effective instruction files that guide Copilot to produce high-quality, consistent code

## 🔍 Step 1: Understanding Copilot's Decision-Making

When using AI-assisted development in a professional environment, it's crucial to:
- **Understand the AI's reasoning** - Know why suggestions are made
- **Maintain standards** - Ensure consistent code quality across the team
- **Debug effectively** - Investigate when suggestions don't meet expectations

GitHub Copilot provides features specifically designed for professional engineers to address these needs.

### Step 1.1: Inspect Copilot's Decision-Making Process

Understanding how Copilot makes suggestions helps you write better prompts and trust the AI's recommendations. The debug view shows you exactly what context Copilot is using and how it formulates responses.

#### Why This Matters:
- **Improve prompts**: See what context Copilot has access to
- **Debug issues**: Understand why unexpected suggestions appear
- **Build trust**: Transparency in AI decision-making
- **Learn patterns**: Discover what makes effective prompts

#### Instructions:

**Method 1: Using Keyboard Shortcut**
1. Press `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (Mac)
2. Type "Copilot Chat Debug"
3. Select **"Copilot Chat Debug: Focus on Copilot Chat Debug View"**

**Method 2: Through the Copilot Chat Window**
1. Open GitHub Copilot Chat
2. At the top of the Copilot Chat window, click the 3 ellipses `...`
3. Click **"Show Chat Debug View"**

#### What You'll See:

Once the debug panel opens, you can explore:

- **Prompts**: The actual prompts sent to the AI model
- **System Prompts**: Background instructions given to Copilot (from custom instructions, repository context, etc.)
- **Metadata**: Context information, model settings, and parameters
- **Response Details**: How Copilot formulated its suggestions, including tokens used

#### 🔬 Try This Experiment:

1. **Ask a simple question in Copilot Chat:**
   
   Create a prompt asking how the GalleryGrid component handles filtering.
   
   <details>
   <summary>💡 Example Prompt</summary>

   ```
   How does the GalleryGrid component handle filtering?
   ```
   </details>

2. **Open the debug view** to see:
   - What files were included in the context
   - What system prompts were applied
   - How the query was processed

3. **Ask a more complex question:**
   
   Create a prompt that asks to refactor the UploadZone component to use a custom hook for file handling. Use the `@workspace` participant for better context.
   
   <details>
   <summary>💡 Example Prompt</summary>

   ```
   @workspace Refactor the UploadZone component to use a custom hook for file handling
   ```
   </details>

4. **Compare the debug information:**
   - Notice the difference in context files used
   - See how workspace references affect the prompt
   - Observe the system instructions that guide behavior

#### 💡 Pro Tips:
- Use this when Copilot's suggestions seem unexpected - you can see exactly what context it's using
- Check the debug view if you're not getting relevant suggestions - you might need to add more context
- Review system prompts to understand what standards Copilot is following
- Look at token usage to optimize your prompts for efficiency

## 🎛️ Step 2: Utilizing Custom Instructions

Custom instructions are rules that apply to every Copilot interaction.

### Step 2.1: Review Repository Instructions

1. **Open** `.github/copilot-instructions.md` in this repository

2. **Notice how it defines:**
   - Project overview and architecture
   - Component patterns
   - Styling conventions
   - Development workflow

3. **Understand how these instructions:**
   - Automatically apply to all Copilot interactions
   - Guide code generation to follow project patterns
   - Maintain consistency across the codebase

#### Example Instructions in This Repo:

The repository instructions file (copilot-instructions.md) includes:
- Project structure overview
- Component usage patterns
- Technology stack information
- Styling conventions
- Best practices for this specific project

These instructions help Copilot generate code that fits seamlessly into the existing codebase.

### Step 2.2: Auto-Generate Repository Instructions

Use the Copilot Chat "Generate Chat Instructions" feature to automatically create (or refine) the repository's `copilot-instructions.md`, then compare and improve it.

1. Open Copilot Chat  
2. Click the gear icon (Configure Chat) → choose **Generate Chat Instructions**
3. Look through the changes that Copilot has suggested making to the instructions file
4. Accept the changes that you think add value to the instructions, and `Undo` the ones that don't

> Tip: You should repeat this process routinely to ensure that the instructions always stay up to date with the codebase. This ensures that Copilot gets the best context possible when working within your code.

## 📊 Step 3: Managing Model Usage and Costs

Understanding premium request usage and model costs is essential for optimizing your GitHub Copilot experience. GitHub Copilot offers different AI models, including some with unlimited usage (0x models) and others that count against a monthly request allowance (premium models). 

Learning to monitor your usage, select the right model for each task, and manage costs effectively will help you work more efficiently. 

For comprehensive information about pricing structures, advanced monitoring strategies, cost optimization techniques, and model selection guidelines by task type, see the **[Premium Request Usage Guide](../docs/Premium-Request-Usage.md)**.

### Step 3.1: Experiment with Model Switching

Different AI models excel at different tasks. Learning which models work best for specific scenarios helps you work more efficiently.

#### Available Models:

GitHub Copilot provides access to models from:
- **OpenAI** (GPT series)
- **Anthropic** (Claude series)
- **Google** (Gemini series)
- **Auto** - Automatically selects the best model for your task at a 10% discount
- **Others** (constantly evolving)

For current models: [Supported Models Documentation](https://docs.github.com/copilot/reference/ai-models/supported-models)

#### About Auto Model Selection:

The **Auto** option intelligently selects the most appropriate model for your specific task:
- **Cost Savings**: Automatically get a 10% discount on premium request usage
- **Smart Selection**: GitHub analyzes your prompt and selects the optimal model
- **Simplified Workflow**: No need to manually choose between models for different tasks
- **Best Practice**: Ideal when you're unsure which model is best suited for your task

When to use Auto:
- When you want cost optimization without manual model selection
- For varied tasks where different models might be optimal
- When you're new to Copilot and learning which models work best
- For general development work without specific model requirements

#### Instructions:

Let's try the same coding task with different models and compare results.

1. **Update your mode to Agent**

2. **Add context files:**
   - Click `Add Context` in GitHub Copilot Chat
   - Add these files:
     - `/src/app/gallery/page.tsx`
     - `/src/lib/mock-photo-data.ts`
     - `/src/components/gallery/GalleryGrid.tsx`
   
   **Alternative method:**
   - Close all tabs
   - Open only these three files
   - Click `Add Context` → `Open Editors`

3. **Stay on GalleryGrid.tsx and highlight lines 26-43**

4. **Select the Auto Model** from the model selector in Copilot Chat

5. **Ask a refactoring question:**
   
   Create a prompt asking Copilot to refactor the selected function for better performance, readability, and TypeScript improvements.
   
   <details>
   <summary>💡 Example Prompt</summary>

   ```
   Help me refactor this function for better performance, readability, and add TypeScript improvements
   ```
   </details>

6. **Note the response** - save or copy it for comparison

7. **Repeat steps 4-6 with two other models**

#### 💡 Comparison Questions:

After trying multiple models, discuss or consider:
- Which model gave the most comprehensive explanation?
- Which provided the best code quality?
- Which was fastest to respond?
- Which model's approach did you prefer and why?
- How did performance recommendations differ?
- Were TypeScript improvements consistent across models?

#### When to Use Different Models:

Based on typical strengths (check current docs for specifics):
- **Quick code completions**: Fast, efficient models
- **Complex refactoring**: Models good at reasoning
- **Explanations**: Models with detailed communication
- **Performance optimization**: Models with deep analysis

## 💎 Step 4: Best Practices for Creating Effective Instruction Files

Creating high-quality instruction files is essential for maximizing Copilot's effectiveness in production environments. Well-crafted instructions help teams maintain consistency, enforce standards, and guide AI-assisted development.

### Why Instruction Files Matter in Real Projects

In real-world development scenarios, instruction files serve several critical purposes:

- **Team Consistency**: Ensure all team members receive similar guidance from Copilot, regardless of their experience level
- **Code Quality**: Automatically enforce architectural patterns and coding standards across the project
- **Faster Onboarding**: Help new developers understand project conventions quickly without extensive documentation reviews
- **Enhanced Copilot Output**: Copilot is tuned to your repository specifics, and as such is much more accurate with its output

### Key Elements of Effective Instructions

When creating instruction files for your projects, focus on these essential elements:

1. **Architecture Patterns**: Be specific about folder structure, design patterns, and code organization
2. **Technology Stack**: Clearly define frameworks, libraries, and versions in use
3. **Code Style**: Specify naming conventions, file structure, and formatting preferences
4. **Component Patterns**: Document where different components live and how they should be structured
5. **Error Handling**: Define consistent approaches to error management and logging
6. **Security Requirements**: Specify security practices that should be followed
7. **Testing Standards**: Set expectations for test coverage and testing approaches
8. **Performance Guidelines**: Include optimization patterns and best practices
9. **Project-Specific Patterns**: Tailor instructions to your domain (e-commerce, recipes, etc.)

## 📋 Step 5: Working with Agent Skills

With a solid understanding of Custom Instructions established, let's turn our attention towards Agent Skills. Agent Skills are customizable, shareable, reusable directories containing tools to help Copilot complete specialized workflows dynamically.

### Step 5.1: Reviewing Built-In Skills

Before we begin crafting our own skills, let us take a look at those included by default within VS Code.

#### Instructions

1. **Inside Chat view, click the Configure Chat cogwheel to open up the Agent Customization editor**

2. **Select the "Skills" tab**

3. **If it is not expanded, click the "Built-In" section, then select "create-instructions"**

4. **Consider the following:**
   - What does this skill do?
   - How might you use this for your team's work?
   - What might the prompt or conversation have looked like that generated the instructions file you viewed in step 2.1?

### Step 5.2: Creating your first Skill

With an understanding of what a skill file generally might look like, we will now create our own with Copilot's help! If you are unsure of your syntactical options, don't be afraid to check out the documentation [here](https://code.visualstudio.com/docs/copilot/customization/agent-skills#_skillmd-file-format)!

#### Instructions

1. **Inside the Agent Customization editor, click "Skills" then select "create-skill"**

2. **Take a moment to understand the contents of this built-in skill and what is required to utilize it**

3. **Close the Agent Customization editor and return to Copilot Chat**

4. **Inside your chat window, type `/create-skill` followed by a prompt detailing functionality that might be useful as a reusable skill**
<details>
   <summary>Fun Suggestion</summary>
   `/create-skill Generate a skill that provides information about a randomly selected CWE entry.`
</details>

5. **With GitHub Copilot's help, iterate until you have a working Skill**

6. **To verify the Skill works correctly, type `/{your skill's name}` and see if it is visible**

7. **Create a prompt that utilizes your Skill, and see how Copilot adapts its answer to compensate** 

### 📖 Complete Guide

For comprehensive best practices, detailed real-world examples, and implementation strategies for creating effective instruction files, see:

**[Copilot Instruction Best Practices Guide](../docs/Copilot-Instruction-Best-Practices.md)**

This reference guide covers:
- Detailed examples for each best practice
- Real-world scenarios for different project types
- Advanced tips for versioning and maintaining instructions
- Common pitfalls to avoid
- Measuring effectiveness of your instruction files

## 🏆 Exercise Wrap-up

Excellent work! You've learned professional engineering practices and instruction customization for GitHub Copilot:
- ✅ Debugged and inspected Copilot's decision-making process using the Debug Panel
- ✅ Configured personal instructions for consistent code generation
- ✅ Monitored premium request usage to optimize costs
- ✅ Experimented with different AI models for various tasks
- ✅ Understood custom instructions hierarchy (personal, repository, organization)
- ✅ Learned best practices for creating effective instruction files

### Reflection Questions:
1. **How can the debug view help you write better prompts?**
2. **How might personal instructions improve your daily workflow?**
3. **What standards or preferences would you include in personal instructions?**
4. **How can monitoring usage help you make better model choices?**
5. **What differences did you notice between AI models?**
6. **What should go in personal vs. repository vs. organization instructions?**
7. **How can well-crafted instructions improve team productivity?**

### Key Takeaways:
- The Debug Panel provides transparency into AI decision-making
- Personal instructions maintain consistency across all your projects
- Repository instructions ensure team-wide coding standards
- Different AI models have different strengths and costs - choose wisely
- Instructions at different levels provide appropriate context (personal, repository, organization)
- These practices make AI-assisted development more professional and reliable
- Well-crafted instruction files multiply Copilot's effectiveness

## Coming up next...

In the next lab, you'll learn about Prompt Files:
- Understand the structure and power of prompt files
- Explore existing prompt files in the repository
- Create your own custom prompt files for common tasks
- Master advanced techniques like multiple variables and workspace context
