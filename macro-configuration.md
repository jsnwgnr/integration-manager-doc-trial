# Macro Configuration

### Overview <a href="#macroconfiguration-overview" id="macroconfiguration-overview"></a>

Macros use a hierarchy to allow flexibility (and privacy) across your deployed integrations.

In a nutshell the macros are applied and overridden in the following order: Public → Template → Private → Configuration → Job

<figure><img src="https://actian.atlassian.net/wiki/download/attachments/15008081/MacroHierarchy.png?version=1&#x26;modificationDate=1644499020000&#x26;cacheVersion=1&#x26;api=v2" alt=""><figcaption></figcaption></figure>

### Account (Public) Macros <a href="#macroconfiguration-account-public-macros" id="macroconfiguration-account-public-macros"></a>

Account-level macros are global and read-only.&#x20;

They can be viewed by all users in your account. They can only be created, edited, deleted by account admin users.

### Template Macros <a href="#macroconfiguration-templatemacros" id="macroconfiguration-templatemacros"></a>

Template macros increase portability of your integrations. They will apply to any configuration that is a child of this template.

They can be viewed by any user who has at least read access to the template. They can only be created, edited, deleted with write access to the template, by the template owner, or by account admin users.

Templates are designed to allow reuse of common integration artifacts and configuration values that apply to multiple integration configurations. For example, you may have several customers or departments within your company who send you the same data format. You could create a single integration template to hold your common integration artifacts (maps, scripts, etc) and common macro values, then create a separate configuration for each - where you only need to override a few macro values that are specific to them.

Note that templates are completely optional. Many configurations will not have a template. This layer of the hierarchy will be ignored for any configurations without a template.

### User (Private) Macros <a href="#macroconfiguration-user-private-macros" id="macroconfiguration-user-private-macros"></a>

User macros can further increase the portability AND privacy of your integrations. User macros are applied for the **submitted by** user when a job is executed. Submitted by will always be the configuration owner for scheduled jobs.

They can only be viewed, created, edited, deleted by the associated user, or by account admin users.

User macros are great for individual users to manage their own credentials to connected systems.

### Configuration Macros <a href="#macroconfiguration-configurationmacros" id="macroconfiguration-configurationmacros"></a>

They can be viewed by any user who has at least read access to the configuration. They can only be created, edited, deleted with write access to the configuration, by the configuration owner, or by account admin users.

### Importing Macros <a href="#macroconfiguration-importingmacros" id="macroconfiguration-importingmacros"></a>

You can import macros directly from a file to any object (Account, Template, User, Configuration).

Import Macro File supports v9 (xml) and later (json) macrodef file formats.

Note that imported macrodef files with encrypted values will only import the macro name, the value will be empty.

### Using the Secure Flag <a href="#macroconfiguration-usingthesecureflag" id="macroconfiguration-usingthesecureflag"></a>

You can permanently encrypt macro values by using the Secure flag. Once a macro is flagged as secure, it can never be read outside of the integration engine runtime.

When you set a macro as secure, it is masked at all levels of the Integration Manager application and can never be "revealed" directly, including from the UI, the API, or any logging mechanism.

Note that secure macros can still be edited and/or deleted by users with write permission to the macro parent object, but the value can never be viewed (by anyone).
