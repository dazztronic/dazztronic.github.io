+++
title = "Building Protected MCP Servers — Den Delimarsky and Julia Kasper, MCP Steering Committee & Microsoft"
date = 2025-12-08
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Software engineering--Artificial intelligence","Computer security","Cloud computing"]
tags = ["MCP","OAuth","Protected Resource Metadata (PRM)","ASP.NET Core","Azure API Management","Microsoft Entra ID","Okta","Auth0","Keycloak","VS Code","GitHub Copilot","REST API","C#"]

[extra]
excerpt = "This session unveils a new, streamlined approach to securing remote MCP servers by decoupling authorization logic from the server implementation, leveraging off-the-shelf identity providers and a standardized Protected Resource Metadata (PRM) mechanism. The presenters emphasize practical, developer-friendly workflows that eliminate the need for deep security expertise, enabling rapid and secure MCP server deployment. The approach is highly actionable, with live demonstrations and direct integration into Azure API Management and VS Code environments."
video_url = "https://www.youtube.com/watch?v=PHBGhUKAM-w"
video_id = "PHBGhUKAM-w"
cover = "https://img.youtube.com/vi/PHBGhUKAM-w/maxresdefault.jpg"
+++

## Overview

This session unveils a new, streamlined approach to securing remote MCP servers by decoupling authorization logic from the server implementation, leveraging off-the-shelf identity providers and a standardized Protected Resource Metadata (PRM) mechanism. The presenters emphasize practical, developer-friendly workflows that eliminate the need for deep security expertise, enabling rapid and secure MCP server deployment. The approach is highly actionable, with live demonstrations and direct integration into Azure API Management and VS Code environments.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The distinctive methodology lies in shifting the burden of OAuth token management and authorization away from MCP server implementers to external, standards-compliant authorization servers (e.g., Entra ID, Okta, Auth0), using a PRM document to bootstrap the OAuth flow. This enables developers to focus on core functionality without becoming security experts, and allows seamless integration with existing enterprise identity infrastructure. The approach is both pragmatic and forward-looking, reflecting real-world developer needs and security best practices.

### The Core Problem
Remote MCP servers, often exposed to the public internet, require robust authorization to protect sensitive APIs and user data. Historically, developers were forced to implement complex, error-prone authorization logic themselves, increasing risk and development overhead—especially for those without deep security backgrounds.

### The Solution Approach
The new draft MCP specification introduces a clear separation of concerns: the MCP server (resource server) no longer mints or manages tokens, but instead points clients to an external authorization server via a PRM document. The client performs the OAuth 'dance' (discovery, token acquisition) using standard libraries, then presents the token to the MCP server, which only needs to validate it. This is demonstrated with minimal C# code using ASP.NET Core, where authentication and PRM metadata are configured declaratively. Azure API Management further simplifies the process by allowing REST APIs to be transformed into MCP servers with built-in security and hosting.

### Key Insights
- Decoupling authorization logic from MCP servers dramatically reduces security risk and development complexity, as most developers are not security experts.
- The PRM (Protected Resource Metadata) document acts as a self-describing endpoint for clients, enabling dynamic discovery of supported authorization flows and scopes.
- Relying on off-the-shelf identity providers (e.g., Entra ID, Okta) is both safer and more scalable than rolling custom authorization code.
- The new spec is designed to be backward-compatible and developer-friendly, with support already landing in tools like VS Code Insiders.
- Transforming existing REST APIs into MCP servers is now a low-friction process via Azure API Management, accelerating enterprise adoption.

### Concepts & Definitions
- "Protected Resource Metadata (PRM)": A JSON document hosted by the MCP server that describes its authorization requirements, supported identity providers, and scopes.
- "Resource server": The MCP server that exposes protected APIs, distinct from the authorization server.
- "Authorization server": External service (e.g., Entra ID, Okta) responsible for minting and managing OAuth tokens.
- "OAuth dance": The step-by-step process by which a client discovers authorization endpoints, obtains user consent, and receives a token.

### Technical Details & Implementation
- ASP.NET Core server setup: add authentication with MCP scheme, configure token validation, inject PRM metadata specifying supported authorization servers and scopes.
- PRM document: JSON (or JWT) hosted by the MCP server, referenced in the WWW-Authenticate header on 401 responses, detailing authorization endpoints and supported methods.
- Client workflow: On 401, client fetches PRM, discovers authorization server, completes OAuth flow, and retries request with token.
- Azure API Management: REST endpoints can be exposed as MCP tools with built-in OAuth security and hosting, requiring minimal configuration.
- C# SDK: Both server and client code are highly declarative, relying on framework defaults and minimal custom logic.

### Tools & Technologies
- ASP.NET Core (for MCP server implementation)
- C# MCP SDK (official, with PR support for new spec)
- Azure API Management (for transforming REST APIs into MCP servers)
- Microsoft Entra ID, Okta, Auth0, Keycloak (as supported identity providers)
- VS Code Insiders (client supporting new authorization spec)
- GitHub Copilot (for tool invocation and testing)

### Contrarian Takes & Different Approaches
- Contrary to the traditional approach of bundling authorization logic with application servers, the presenters advocate for strict separation and externalization of security concerns.
- They challenge the notion that every developer should be a security expert, instead promoting reliance on robust, external identity providers.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Adopt the new MCP spec to offload authorization to trusted identity providers—stop writing custom token logic.
- Leverage the PRM mechanism to make your MCP server self-describing and interoperable with standard OAuth flows.
- Use Azure API Management to quickly convert REST APIs into secure MCP servers, minimizing manual setup.
- Rely on official SDKs and framework defaults for authentication and token validation—avoid reinventing security code.
- Test your setup with VS Code Insiders and GitHub Copilot to validate end-to-end tool integration.

### What to Avoid
- Avoid implementing your own authorization server logic unless you are a security expert—it's error-prone and risky.
- Do not expose remote MCP servers without proper authorization, especially if accessible from the public internet.
- Beware of skipping the PRM step—clients need this metadata to correctly bootstrap the OAuth flow.
- Neglecting to validate tokens on the server side is a critical security flaw.

### Best Practices
- Always delegate token minting and management to established identity providers.
- Expose PRM metadata in a standard way to enable seamless client discovery and integration.
- Use declarative configuration for authentication and authorization in your server code.
- Leverage platform tools (like Azure API Management) to automate security and hosting concerns.

### Personal Stories & Experiences
- Always delegate token minting and management to established identity providers.
- Expose PRM metadata in a standard way to enable seamless client discovery and integration.
- Use declarative configuration for authentication and authorization in your server code.
- Leverage platform tools (like Azure API Management) to automate security and hosting concerns.

### Metrics & Examples
- No explicit quantitative metrics are cited, but the demonstration shows a reduction in code complexity and configuration steps compared to previous approaches.
- Live demo: Successful end-to-end tool invocation in VS Code after integrating PRM and external authorization.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=PHBGhUKAM-w)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
