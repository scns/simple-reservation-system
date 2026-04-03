=== WP Plugin Factory Reservation System ===
Contributors: wppluginfactory, schmeitzm
Donate link: https://wppluginfactory.nl/
Tags: reservations, booking, calendar, appointments, ical
Requires at least: 6.2
Tested up to: 6.9
Requires PHP: 7.4
Stable tag: 2.5.6
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

A complete reservation and booking system with an interactive calendar, iCal integration, and capacity-aware scheduling.

== Description ==

Simple Reservation System is a fully-featured reservation and booking plugin for WordPress. It allows your visitors to create, manage, and track reservations through an intuitive, responsive calendar interface powered by FullCalendar.

Whether you manage meeting rooms, sports courts, equipment, desks, or any other bookable resource — this plugin gives you and your users everything needed to handle reservations efficiently.

= Key Features =

* **Interactive Calendar** — Powered by FullCalendar 6 with month, week, day, and list views
* **Resource Management** — Create unlimited resources (rooms, equipment, vehicles, etc.) with name, description, capacity, and color
* **Capacity-Aware Scheduling** — Shared time slots with automatic capacity tracking, or classic one-booking-per-slot mode
* **User Self-Service** — Users register, log in, and manage their own reservations
* **Admin Management Portal** — Full overview with filters, bulk actions, and the ability to create reservations on behalf of users
* **iCal Integration** — Personal and admin iCal feeds, .ics import/export, and .ics email attachments
* **Email Notifications** — Customizable templates with placeholders for booking confirmations, updates, and cancellations
* **Configurable Business Hours** — Set opening hours per day of the week with enable/disable per day
* **Cancellation Policy** — Configurable: allow or disallow cancellation with a minimum advance time
* **Mobile Responsive** — Automatic list-view fallback on small screens with configurable breakpoint
* **Reports & Statistics** — Chart.js-powered dashboards with per-day, per-user, per-resource, and per-status breakdowns
* **REST API** — Full CRUD API for custom integrations with public, authenticated, and admin endpoints
* **Multilingual** — Ships with Dutch (NL), English (US), German (DE), and French (FR) translations
* **Developer Friendly** — Action hooks for reservation created, updated, and deleted events

= Available Shortcodes =

* `[wppluginfactory_calendar]` — Display the interactive reservation calendar
* `[wppluginfactory_calendar resource="3"]` — Calendar filtered to a specific resource
* `[wppluginfactory_reservation_form]` — Standalone reservation form with date/time picker
* `[wppluginfactory_reservation_form resource="3"]` — Reservation form pre-filtered to a resource
* `[wppluginfactory_my_reservations]` — Logged-in user's reservation overview with edit and cancel options
* `[wppluginfactory_login]` — AJAX login form (no page reload)
* `[wppluginfactory_register]` — AJAX registration form with first name, last name, phone, and password
* `[wppluginfactory_profile]` — User profile editor with iCal feed URL and copy button

= Admin Pages =

* **Dashboard** — At-a-glance statistics, calendar preview, recent reservations, shortcode reference, admin iCal feed URL
* **All Reservations** — Searchable, filterable list of all reservations with inline editing and creation
* **Resources** — Create, edit, and delete resources with capacity and color settings
* **Calendar** — Full calendar view with iCal import and export
* **Reports** — Visual reports with date range, resource, and user filters
* **Settings** — All plugin configuration options
* **License** — License activation, verification, trial request, and upgrade

= License Tiers =

Simple Reservation System is available in two license tiers:

**Lite** — Perfect for small businesses with basic booking needs:

* Basic reservation system with calendar
* Max 50 reservations per month
* Max 1 resource
* Basic email notifications
* No reports & statistics
* No iCal feeds
* No priority support

**Full** — The complete package for growing businesses:

* Unlimited reservations
* Unlimited resources
* Full email notifications with .ics attachments
* Reports & statistics dashboards
* iCal import/export feeds
* Priority support

= Source Code & Contributions =

The source code, release downloads, and issue tracker are hosted on [GitHub](https://github.com/scns/wppluginfactory-reservation-system).

* **Download latest release** — [github.com/scns/wppluginfactory-reservation-system/releases](https://github.com/scns/wppluginfactory-reservation-system/releases)
* **Bug reports & feature requests** — [github.com/scns/wppluginfactory-reservation-system/issues](https://github.com/scns/wppluginfactory-reservation-system/issues)
* **Documentation & changelogs** — available in the repository README and release notes

= REST API Endpoints =

The plugin registers a comprehensive REST API under the `wppluginfactory/v1` namespace:

**Public (no authentication required):**

* `GET /wppluginfactory/v1/events` — Calendar events (params: start, end, resource)
* `GET /wppluginfactory/v1/slots` — Available time slots (params: date, resource)
* `GET /wppluginfactory/v1/resources` — All active resources

**Authenticated (logged-in users):**

* `GET /wppluginfactory/v1/reservations` — List user's reservations
* `POST /wppluginfactory/v1/reservations` — Create a reservation
* `GET /wppluginfactory/v1/reservations/{id}` — Get a single reservation
* `PUT /wppluginfactory/v1/reservations/{id}` — Update own reservation
* `DELETE /wppluginfactory/v1/reservations/{id}` — Delete own reservation
* `GET /wppluginfactory/v1/my-reservations` — Current user's reservations

**Admin (requires `wppluginfactory_manage_reservations` capability):**

* `GET /wppluginfactory/v1/admin/reservations` — All reservations with advanced filters
* `POST /wppluginfactory/v1/admin/reservations` — Create reservation on behalf of a user
* `PUT /wppluginfactory/v1/admin/reservations/{id}` — Update any reservation
* `DELETE /wppluginfactory/v1/admin/reservations/{id}` — Delete any reservation
* `GET /wppluginfactory/v1/admin/stats` — Dashboard statistics
* `GET /wppluginfactory/v1/admin/reports` — Detailed reports with filters
* `GET /wppluginfactory/v1/admin/users` — Search users
* `GET /wppluginfactory/v1/admin/check-conflict` — Proactive availability check

= Email Template Placeholders =

Customize your notification emails with these placeholders:

* `{naam}` — Customer name
* `{titel}` — Reservation title
* `{resource}` — Resource name
* `{start}` — Start date/time
* `{eind}` — End date/time
* `{gasten}` — Number of guests
* `{beschrijving}` — Description
* `{site}` — Website name

= iCal Template Placeholders =

Customize the content of iCal calendar files (Full license only) with these placeholders:

* `{titel}` — Reservation title
* `{resource}` — Resource name
* `{start}` — Start date/time
* `{eind}` — End date/time
* `{gasten}` — Number of guests
* `{beschrijving}` — Description
* `{notities}` — Notes
* `{naam}` — Customer name
* `{site}` — Website name

= Developer Hooks =

* `wppluginfactory_reservation_created` — Fires after a reservation is created (args: $id, $data)
* `wppluginfactory_reservation_updated` — Fires after a reservation is updated (args: $id, $data)
* `wppluginfactory_reservation_before_delete` — Fires before a reservation is deleted (args: $id, $existing)

= Third-Party Libraries =

* [FullCalendar](https://fullcalendar.io/) 6.1.9 — Interactive calendar rendering (MIT License)
* [Chart.js](https://www.chartjs.org/) 4.4.4 — Reports and statistics charts (MIT License)

Both libraries are bundled locally and no external CDN requests are made.

== Installation ==

1. Upload the `wppluginfactory-reservation-system` folder to `/wp-content/plugins/`
2. Activate the plugin through the **Plugins** menu in WordPress
3. Go to **Reservations > License** and activate your license key, or request a free trial
4. Configure your settings under **Reservations > Settings**
5. Add resources (rooms, equipment, etc.) under **Reservations > Resources**
6. Create a page and add the `[wppluginfactory_calendar]` shortcode to display the calendar
7. Optionally add `[wppluginfactory_login]`, `[wppluginfactory_register]`, `[wppluginfactory_my_reservations]`, and `[wppluginfactory_profile]` shortcodes to other pages

= Minimum Requirements =

* WordPress 6.2 or higher
* PHP 7.4 or higher
* MySQL 5.6 or higher / MariaDB 10.1 or higher

== Frequently Asked Questions ==

= Do I need a license? =

Yes, a valid license key is required to use this plugin. You can request a free 1-month trial license from the **Reservations > License** page, or purchase a full license at [wppluginfactory.nl](https://wppluginfactory.nl). Each domain can only request one trial.

= How do users make reservations? =

Users register through the `[wppluginfactory_register]` shortcode or the built-in registration form. Once logged in, they can click on the calendar to create reservations, or use the standalone `[wppluginfactory_reservation_form]` shortcode.

= Can users manage their own reservations? =

Yes. The `[wppluginfactory_my_reservations]` shortcode shows each user their own reservations where they can view details, edit, or cancel them (subject to your cancellation policy settings).

= What is shared slot / capacity mode? =

When enabled under **Reservations > Settings**, multiple users can book the same time slot as long as the total number of guests does not exceed the resource's capacity. For example, a room with capacity 10 can have multiple reservations simultaneously, until all 10 spots are filled. When disabled, each time slot can only have one reservation.

= Can admins create reservations on behalf of users? =

Yes. In the admin panel under **All Reservations**, administrators can create new reservations and select any registered user as the owner. There is also a user search function to find users by name or email.

= Does it support iCal? =

Yes, in multiple ways:

* **Personal iCal Feed** — Each user gets a personal iCal feed URL (visible on the `[wppluginfactory_profile]` page) that syncs their reservations to Google Calendar, Apple Calendar, Outlook, or any iCal-compatible app.
* **Admin iCal Feed** — Administrators get a feed URL with all reservations across all users.
* **Import/Export** — Admins can import .ics files into a resource and export all reservations as .ics files.
* **Email Attachments** — Confirmation and update emails can include .ics attachments so users can add events to their calendar with one click.

= Can I customize the email notifications? =

Yes. Under **Reservations > Settings** you can customize the sender name, sender email, and the subject and body templates for five types of notifications: created, updated, cancelled, pending, and approved. Use placeholders like `{naam}`, `{titel}`, `{start}`, etc.

= Can I customize the iCal file content? =

Yes (Full license only). Under **Reservations > Settings > iCal / Calendar Template** you can customize the calendar name (`X-WR-CALNAME`), the event title (`SUMMARY`), and the event description (`DESCRIPTION`) for all generated iCal files — including personal feeds, the admin feed, and .ics email attachments. Use the same placeholder variables listed in the iCal Template Placeholders section. Lite users receive the built-in default layout.

= Can I set business hours? =

Yes. Under **Reservations > Settings** you can configure opening and closing times for each day of the week (Monday through Sunday). Each day can be enabled or disabled individually. Only time slots within business hours will be available for booking.

= What resources can I manage? =

Resources can represent anything you want to make bookable: meeting rooms, desks, sports courts, equipment, vehicles, studios, etc. Each resource has a name, description, capacity (number of guests), a display color, and an active/inactive status.

= Is it mobile responsive? =

Yes. The calendar automatically switches to a list view on screens smaller than the configured breakpoint (default: 768px). Both the calendar and all forms are fully responsive.

= Can I customize the colors? =

Yes. Under **Reservations > Settings** you can set a primary color that affects the calendar and UI. Additionally, each resource has its own display color that appears on the calendar.

= Does the plugin create custom database tables? =

Yes. The plugin creates three custom tables on activation:

* `{prefix}_wppluginfactory_resources` — Stores resources
* `{prefix}_wppluginfactory_reservations` — Stores all reservations
* `{prefix}_wppluginfactory_settings` — Stores plugin settings

= Is there a REST API? =

Yes. The plugin provides a full REST API under the `wppluginfactory/v1` namespace with public, authenticated, and admin-only endpoints. See the Description section for the complete endpoint list.

= What languages are included? =

The plugin ships with translations for Dutch (NL), English (US), German (DE), and French (FR). You can add your own translations using the included `.pot` template file.

= How do I set up a cancellation policy? =

Under **Reservations > Settings > Cancellation**, you can:

* Enable or disable user cancellations entirely
* Set a minimum number of hours before the reservation start time that cancellations are allowed (e.g., 24 hours means users cannot cancel within 24 hours of their reservation)

== Screenshots ==

1. Interactive calendar view with month, week, day, and list options
2. Reservation form with resource selection, time slots, and guest count
3. Admin dashboard with statistics and quick actions
4. Resource management with capacity and color settings
5. Reports with Chart.js visualizations
6. Email notification settings with customizable templates
7. User profile with iCal feed URL
8. Mobile responsive list view

== Changelog ==

= 2.5.6 =
* Fixed: Release pipeline now correctly publishes to public repo in a single workflow (resolves trigger limitation with GITHUB_TOKEN)

= 2.5.5 =
* Fixed: Cancelling a reservation no longer sends two emails (a "modified" notification followed by a "cancelled" notification) — only the cancellation confirmation is now sent
* Added: All-day admin reservations now have a "Block resource" toggle — checked (default) blocks the resource so no new bookings can be made; unchecked shows the event on the calendar without blocking existing time slots
* Changed: Plugin slug and all code prefixes renamed from WRS/wrs to WPPluginfactory/wppluginfactory for WordPress.org compliance
* Added: Migration function automatically copies existing reservations, resources and settings from the old wrs_ database tables to the new wppluginfactory_ tables on first load
* Fixed: REST API /events endpoint now always returns busy-only data to unauthenticated users, regardless of the calendar privacy setting
* Updated: FullCalendar library updated from 6.1.9 to 6.1.20
* Fixed: Plugin URI corrected (was a 404)
* Updated: Tested up to WordPress 6.9

= 2.5.3 =
* Added: iCal template settings (Full only) — customize calendar name, event title (SUMMARY), and event description (DESCRIPTION) via **Reservations > Settings > iCal / Calendar Template**
* Added: Placeholder support for iCal templates: `{titel}`, `{resource}`, `{start}`, `{eind}`, `{gasten}`, `{beschrijving}`, `{notities}`, `{naam}`, `{site}`
* Added: Lite users continue to use the built-in default iCal layout (no change in behavior)
* Added: iCal template fields are read-only for Lite users with an upgrade notice
* Fixed: iCal DESCRIPTION showed only first line when template contained multiple lines (CRLF from textarea was not normalized before iCal escaping)
* Added: Guest count minimum enforced at 1 on both frontend and server side
* Fixed: License "last verified" timestamp showed -1 day(en) geleden on servers with a non-UTC timezone — `last_verified` is now stored as UTC (`current_time('mysql', true)`) so the diff against `time()` is always correct
* Fixed: Translation files (de_DE, en_US, fr_FR, nl_NL) contained invalid `\uXXXX` JSON-style escape sequences — replaced with literal UTF-8 characters and recompiled all .mo files using msgfmt
* Changed: Minimum required WordPress version raised from 5.8 to 6.2

= 2.5.2 =
* Improved: "All Reservations" overview now shows only today and future reservations by default
* Added: "Show past" button to reveal historical reservations (toggles to "Hide past" when active)
* Fixed: Reset button restores the default filter (today and later) instead of clearing all filters
* Added: Reservation ID in the overview table is now a clickable link that opens the edit screen inline

= 2.5.1 =
* Fixed: Fatal error on plugin activation when two plugin versions coexist during WordPress update (added early-bailout guard and `defined()` checks for all constants and classes)
* Fixed: Reservation edit modal not opening when clicking a reservation number link from the activity log or calendar
* Added: GET `admin/reservations/{id}` REST endpoint to fetch a single reservation as admin
* Added: Reservation ID column in admin reservations table is now a direct link that opens the edit modal inline
* Added: Clicking an event in the admin dashboard calendar now opens the reservations page with the edit modal pre-opened
* Added: `maybeOpenReservationFromUrl()` — URL param `?open={id}` on the reservations page opens the edit modal automatically

= 2.5.0 =
* Added: Lite and Full license tiers with feature gating
* Added: Lite restrictions — max 1 resource, 50 reservations/month, no reports, no iCal
* Added: Admin approval workflow — reservations can be set to require manual approval before confirmation (Full only)
* Added: Pending reservation status with dedicated admin approval button
* Added: Re-pending on user edit — when approval mode is on and a user edits their reservation, status resets to pending
* Added: Public calendar privacy mode — busy-only option hides reservation details from non-admins
* Added: Activity log page (Full only) — full audit trail of all reservation changes with filters and pagination
* Added: License last-verified timestamp — displayed on the license page with a visual indicator
* Added: Admin banner when license verification is older than 5 days
* Added: Approved and Pending email notification templates
* Added: Email from name and from address settings
* Added: Admin notice showing Lite limitations with upgrade link
* Added: License type (Lite/Trial badge) displayed on license management page
* Fixed: Email template fields lost their values on save due to use of `disabled` HTML attribute — changed to `readonly`
* Fixed: Email from name and from address lost values on save — same `disabled` → `readonly` fix
* Fixed: Non-admins blocked from editing past reservations (API returns 403, frontend hides buttons)
* Fixed: Edit and Cancel buttons hidden in "My Reservations" for past reservations
* Changed: Admin calendar privacy check uses `manage_options` instead of `wppluginfactory_manage_reservations`
* Changed: Plugin URI → https://www.wppluginfactory.nl/wp-reservation/
* Changed: Author → WP Plugin Factory, Author URI → https://www.wppluginfactory.nl

= 2.4.4 =
* Improved: Reservation form now shows only time slots instead of manual start/end time fields

= 2.4.3 =
* Fixed: iCal feed returned 404 because rewrite rules were not registered before flush on activation
* Fixed: iCal rewrite rule regex now matches tokens containing underscores
* Fixed: iCal times were off by 1 hour due to incorrect timezone conversion (local time was interpreted as UTC)
* Fixed: Fatal error on plugin activation because WPPluginfactory_ICal class was not loaded
* Improved: iCal DESCRIPTION now includes the name of the person who made the reservation, notes, resource, and number of guests

= 2.4.2 =
* Fixed: WordPress Plugin Check compliance — all PHPCS warnings and errors resolved
* Fixed: Replaced `date()` with `gmdate()` throughout the plugin
* Fixed: Added proper input sanitization for all `$_POST` and `$_FILES` variables
* Fixed: Added nonce verification annotations for read-only GET parameters
* Fixed: Added `phpcs:disable/enable` blocks for all custom database queries
* Fixed: License header changed from "Proprietary" to "GPLv2 or later"
* Fixed: Removed `load_plugin_textdomain()` deprecation warning
* Changed: Plugin renamed from "WP Reservation System" to "Simple Reservation System"
* Changed: Text domain changed to `wppluginfactory-reservation-system`
* Changed: Plugin slug changed to `wppluginfactory-reservation-system`
* Changed: Tested up to WordPress 6.9
* Improved: Readme.txt updated to full WordPress.org standard format

= 2.4.1 =
* Added: Translation audit — 37 missing strings added to all 4 languages
* Added: Translators comments for all translatable strings with placeholders
* Fixed: FullCalendar and Chart.js now loaded from local vendor folder instead of CDN
* Fixed: Removed FullCalendar CSS enqueue (CSS is embedded in FullCalendar 6 JS bundle)
* Improved: Recompiled all .mo translation files

= 2.4.0 =
* Added: Admin iCal feed for all reservations
* Added: Shared time slots with capacity-aware booking
* Added: "Full booking" option to book entire resource capacity at once
* Added: All-day blocking for maintenance or closures
* Added: Proactive conflict checking via REST API
* Added: Admin can create reservations on behalf of users with user search
* Added: Mobile responsive list view with configurable breakpoint
* Added: Cancellation policy with configurable minimum advance hours
* Added: Email templates with customizable subjects and body text
* Added: ICS calendar attachments in notification emails
* Added: Color picker for primary theme color
* Added: Reports and statistics with Chart.js charts
* Added: German (DE) and French (FR) translations

= 2.3.0 =
* Added: Resource management with capacity and color
* Added: iCal import and export
* Added: Email notifications for reservation events
* Added: REST API for custom integrations
* Added: Custom user role `wppluginfactory_manager`

= 2.2.0 =
* Added: User registration and login system with AJAX
* Added: User profile management with iCal feed
* Added: Business hours configuration per day

= 2.1.0 =
* Added: Reservation CRUD with conflict detection
* Added: Admin reservation management with filters and search
* Added: Color-coded reservation statuses

= 2.0.0 =
* Major rewrite with FullCalendar 6 integration
* Added: Shortcode system with 6 shortcodes
* Added: License activation system with trial support

= 1.0.0 =
* Initial release

== Upgrade Notice ==

= 2.5.3-beta2 =
Beta 2 release.

= 2.4.2 =
Plugin renamed to "Simple Reservation System" for WordPress.org compliance. Text domain changed — if you have custom translations, rename your .po/.mo files accordingly.

= 2.4.0 =
Major feature update with shared slots, capacity management, admin iCal feed, reports, and mobile responsive improvements. Database schema is unchanged.


