# GTM DataLayer Detective

A Chrome DevTools extension for debugging Google Tag Manager (GTM) implementations and GA4 events in real-time.

## Overview

GTM DataLayer Detective provides a clean, side-by-side view of GTM dataLayer events and GA4 network requests, making it easy to debug and validate your analytics implementation. The extension captures events in real-time and presents them in an organized, developer-friendly interface.

## Features

### Dual-Column Interface
- **Left Column**: GTM dataLayer events with nested key-value pairs
- **Right Column**: GA4 network requests with event parameters and user properties

### Real-Time Event Capture
- Automatically intercepts and displays dataLayer pushes as they happen
- Captures GA4 collect API calls from the network tab
- Continuously monitors for dataLayer initialization and re-initialization (handles SPAs)

### Multi-Container Support
- Automatically detects multiple GTM containers on a page
- Filter events by container ID when multiple containers are present
- Clear visual indication of which container fired each event

### Search & Filter
- Real-time search across both columns
- Searches through event names, parameter names, and values
- Case-insensitive matching
- Shows filtered count in real-time

### Preserve Log
- Toggle to preserve events across page navigations
- Visual indicator when preserve log is active
- Useful for debugging page transitions and redirects

### Data Export
- Export all captured events to JSON format
- Includes both dataLayer events and network requests
- Timestamped export with container information

### Developer-Friendly Display
- Dark theme optimized for DevTools
- Syntax highlighting for different data types (strings, numbers, booleans, null)
- Monospace font for easy reading
- Timestamps for every event
- Expandable nested objects

### Using the Extension

1. Open Chrome DevTools (F12 or Right-click → Inspect)
2. Look for the "GTM DataLayer Detective" tab in the DevTools tabs
3. Navigate to a page with GTM installed
4. Events will appear automatically as they fire

## Usage Guide

### Basic Operations

**Clear Events**
- Click the "Clear" button to remove all captured events from both columns
- Does not affect the actual dataLayer or analytics implementation

**Export Data**
- Click "Export JSON" to download all captured events
- File includes metadata: URL, export timestamp, containers, all events

**Preserve Log**
- Click "Preserve log" to maintain events across page navigations
- Button turns light blue when active
- Click again to disable (button returns to dark grey)

**Search Events**
- Type in the search field to filter events in real-time
- Searches across event names, parameter names, and values
- Clear the search field to show all events

**Filter by Container**
- When multiple GTM containers are detected, a dropdown appears
- Select a specific container to view only its events
- Select "All Containers" to view events from all containers

### Understanding the Display

#### DataLayer Events (Left Column)

Each event shows:
- **Index**: Sequential number (#1, #2, etc.)
- **Timestamp**: When the event was captured
- **Key-Value Pairs**: All properties in the dataLayer push
  - Purple text: Property names
  - Orange text: String values
  - Green text: Number values
  - Blue text: Boolean values
  - Grey text: Null values

#### GA4 Network Requests (Right Column)

Each request shows:
- **Method**: HTTP method (typically GET or POST)
- **Event Name**: The GA4 event name (e.g., page_view, click, scroll_depth)
- **Timestamp**: When the request was sent
- **Parameters**: Event parameters and user properties
  - `ep.*` / `epn.*`: Event parameters (string/numeric)
  - `up.*` / `upn.*`: User properties (string/numeric)
  - All prefixes are stripped for cleaner display

## Technical Details

### Supported Data Types

The extension recognizes and properly displays:
- Strings (orange)
- Numbers (green)
- Booleans (blue)
- Null/undefined (grey)
- Objects (flattened to nested key-value pairs)
- Arrays (stringified)

## Browser Compatibility

- **Chrome**: Fully supported (Manifest V3)
- **Edge**: Fully supported (Chromium-based)
- **Other Chromium browsers**: Should work with Manifest V3 support

## Contributing

This extension was developed to make GTM debugging easier. If you encounter bugs or have feature requests, please document them with:
- Browser version
- Extension version
- Steps to reproduce
- Expected vs actual behavior

## Credits

Developed to simplify Google Tag Manager and GA4 debugging for developers and analysts.

© 2026 Ross Foniri
