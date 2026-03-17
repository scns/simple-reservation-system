=== Simple Reservation System ===
Contributors: scns
Donate link: https://wppluginfactory.nl/
Tags: reservations, booking, calendar, appointments, ical
Requires at least: 5.8
Tested up to: 6.9
Requires PHP: 7.4
Stable tag: 2.5.2
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

* `[wrs_calendar]` — Display the interactive reservation calendar
* `[wrs_calendar resource="3"]` — Calendar filtered to a specific resource
* `[wrs_reservation_form]` — Standalone reservation form with date/time picker
* `[wrs_reservation_form resource="3"]` — Reservation form pre-filtered to a resource
* `[wrs_my_reservations]` — Logged-in user's reservation overview with edit and cancel options
* `[wrs_login]` — AJAX login form (no page reload)
* `[wrs_register]` — AJAX registration form with first name, last name, phone, and password
* `[wrs_profile]` — User profile editor with iCal feed URL and copy button

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

= REST API Endpoints =

The plugin registers a comprehensive REST API under the `wrs/v1` namespace:

**Public (no authentication required):**

* `GET /wrs/v1/events` — Calendar events (params: start, end, resource)
* `GET /wrs/v1/slots` — Available time slots (params: date, resource)
* `GET /wrs/v1/resources` — All active resources

**Authenticated (logged-in users):**

* `GET /wrs/v1/reservations` — List user's reservations
* `POST /wrs/v1/reservations` — Create a reservation
* `GET /wrs/v1/reservations/{id}` — Get a single reservation
* `PUT /wrs/v1/reservations/{id}` — Update own reservation
* `DELETE /wrs/v1/reservations/{id}` — Delete own reservation
* `GET /wrs/v1/my-reservations` — Current user's reservations

**Admin (requires `wrs_manage_reservations` capability):**

* `GET /wrs/v1/admin/reservations` — All reservations with advanced filters
* `POST /wrs/v1/admin/reservations` — Create reservation on behalf of a user
* `PUT /wrs/v1/admin/reservations/{id}` — Update any reservation
* `DELETE /wrs/v1/admin/reservations/{id}` — Delete any reservation
* `GET /wrs/v1/admin/stats` — Dashboard statistics
* `GET /wrs/v1/admin/reports` — Detailed reports with filters
* `GET /wrs/v1/admin/users` — Search users
* `GET /wrs/v1/admin/check-conflict` — Proactive availability check

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

= Developer Hooks =

* `wrs_reservation_created` — Fires after a reservation is created (args: $id, $data)
* `wrs_reservation_updated` — Fires after a reservation is updated (args: $id, $data)
* `wrs_reservation_before_delete` — Fires before a reservation is deleted (args: $id, $existing)

= Third-Party Libraries =

* [FullCalendar](https://fullcalendar.io/) 6.1.9 — Interactive calendar rendering (MIT License)
* [Chart.js](https://www.chartjs.org/) 4.4.4 — Reports and statistics charts (MIT License)

Both libraries are bundled locally and no external CDN requests are made.

== Installation ==

1. Upload the `simple-reservation-system` folder to `/wp-content/plugins/`
2. Activate the plugin through the **Plugins** menu in WordPress
3. Go to **Reservations > License** and activate your license key, or request a free trial
4. Configure your settings under **Reservations > Settings**
5. Add resources (rooms, equipment, etc.) under **Reservations > Resources**
6. Create a page and add the `[wrs_calendar]` shortcode to display the calendar
7. Optionally add `[wrs_login]`, `[wrs_register]`, `[wrs_my_reservations]`, and `[wrs_profile]` shortcodes to other pages

= Minimum Requirements =

* WordPress 5.8 or higher
* PHP 7.4 or higher
* MySQL 5.6 or higher / MariaDB 10.1 or higher

== Frequently Asked Questions ==

= Do I need a license? =

Yes, a valid license key is required to use this plugin. You can request a free 1-month trial license from the **Reservations > License** page, or purchase a full license at [wppluginfactory.nl](https://wppluginfactory.nl). Each domain can only request one trial.

= How do users make reservations? =

Users register through the `[wrs_register]` shortcode or the built-in registration form. Once logged in, they can click on the calendar to create reservations, or use the standalone `[wrs_reservation_form]` shortcode.

= Can users manage their own reservations? =

Yes. The `[wrs_my_reservations]` shortcode shows each user their own reservations where they can view details, edit, or cancel them (subject to your cancellation policy settings).

= What is shared slot / capacity mode? =

When enabled under **Reservations > Settings**, multiple users can book the same time slot as long as the total number of guests does not exceed the resource's capacity. For example, a room with capacity 10 can have multiple reservations simultaneously, until all 10 spots are filled. When disabled, each time slot can only have one reservation.

= Can admins create reservations on behalf of users? =

Yes. In the admin panel under **All Reservations**, administrators can create new reservations and select any registered user as the owner. There is also a user search function to find users by name or email.

= Does it support iCal? =

Yes, in multiple ways:

* **Personal iCal Feed** — Each user gets a personal iCal feed URL (visible on the `[wrs_profile]` page) that syncs their reservations to Google Calendar, Apple Calendar, Outlook, or any iCal-compatible app.
* **Admin iCal Feed** — Administrators get a feed URL with all reservations across all users.
* **Import/Export** — Admins can import .ics files into a resource and export all reservations as .ics files.
* **Email Attachments** — Confirmation and update emails can include .ics attachments so users can add events to their calendar with one click.

= Can I customize the email notifications? =

Yes. Under **Reservations > Settings** you can customize the sender name, sender email, and the subject and body templates for three types of notifications: created, updated, and cancelled. Use placeholders like `{naam}`, `{titel}`, `{start}`, etc.

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

* `{prefix}_wrs_resources` — Stores resources
* `{prefix}_wrs_reservations` — Stores all reservations
* `{prefix}_wrs_settings` — Stores plugin settings

= Is there a REST API? =

Yes. The plugin provides a full REST API under the `wrs/v1` namespace with public, authenticated, and admin-only endpoints. See the Description section for the complete endpoint list.

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

= 2.5.2 =
* Improved: "Alle Reserveringen" overzicht toont standaard alleen reserveringen vanaf vandaag
* Added: "Toon verleden" knop om historische reserveringen zichtbaar te maken (wordt "Verberg verleden" wanneer actief)
* Fixed: Reset-knop herstelt standaardfilter (vandaag en later) in plaats van alle filters te wissen
* Added: Reservering-ID in overzichtstabel is nu een klikbare link die het bewerkscherm direct opent

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
* Added: Pending reservation status with dedicated admin approval button (✓ Goedkeuren)
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
* Changed: Admin calendar privacy check uses `manage_options` instead of `wrs_manage_reservations`
* Changed: Plugin URI → https://www.wppluginfactory.nl/wp-reservation/
* Changed: Author → WP Plugin Factory, Author URI → https://www.wppluginfactory.nl

= 2.4.4 =", "oldString": "= 2.4.4 =
* Improved: Reserveringsformulier toont alleen tijdsloten in plaats van handmatige start/eindtijd velden

= 2.4.3 =
* Fixed: iCal feed returned 404 because rewrite rules were not registered before flush on activation
* Fixed: iCal rewrite rule regex now matches tokens containing underscores
* Fixed: iCal tijden stonden 1 uur verkeerd door onjuiste tijdzone-conversie (lokale tijd werd als UTC geïnterpreteerd)
* Fixed: Fatal error bij plugin-activatie doordat WRS_ICal class niet geladen was
* Improved: iCal DESCRIPTION bevat nu naam van de reserveerder, notities, resource en aantal gasten

= 2.4.2 =
* Fixed: WordPress Plugin Check compliance — all PHPCS warnings and errors resolved
* Fixed: Replaced `date()` with `gmdate()` throughout the plugin
* Fixed: Added proper input sanitization for all `$_POST` and `$_FILES` variables
* Fixed: Added nonce verification annotations for read-only GET parameters
* Fixed: Added `phpcs:disable/enable` blocks for all custom database queries
* Fixed: License header changed from "Proprietary" to "GPLv2 or later"
* Fixed: Removed `load_plugin_textdomain()` deprecation warning
* Changed: Plugin renamed from "WP Reservation System" to "Simple Reservation System"
* Changed: Text domain changed to `simple-reservation-system`
* Changed: Plugin slug changed to `simple-reservation-system`
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
* Added: Custom user role `wrs_manager`

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

= 2.4.2 =
Plugin renamed to "Simple Reservation System" for WordPress.org compliance. Text domain changed — if you have custom translations, rename your .po/.mo files accordingly.

= 2.4.0 =
Major feature update with shared slots, capacity management, admin iCal feed, reports, and mobile responsive improvements. Database schema is unchanged.
