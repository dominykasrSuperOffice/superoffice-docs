---
title: Notifications
uid: dp-notifications
description: Manage app notifications in the SuperOffice Developer Portal.
author: Bergfrid Dias
so.date: 04.27.2023
keywords: Developer Portal, app, notification, error, tenant status
so.topic: howto
so.dp-version: 1.11
so.envir: cloud
so.client:
---

# Manage app notifications

[!include[Intro to tenant status](../../apps/tenant-status/includes/tenant-status-intro.md)]

SuperOffice will also send you emails when there is a problem with your application. By default, these emails go to the technical contact of the application. However, you can also specify a list of addresses for error reporting.

Watch the walk-through on YouTube:

<!-- markdownlint-disable-next-line MD034 DOCSMD007 -->
> [!Video https://www.youtube-nocookie.com/embed/kqEpAw7qQEY?start=1400]

## Tenant status

The **State change URL** is set in the advanced application configuration of each application.

<!-- markdownlint-disable MD029 -->
[!include[Go to the app page](../includes/go-to-app-page.md)]
<!-- List starts in the include. Next line MUST be 2. -->

2. Select **Configuration**.

3. Turn on **Advanced**.

4. Select **Notifications**.

    ![Configure notifications -screenshot][img1]

5. Enter the URL of your endpoint SuperOffice should push notifications to when a tenant changes status.

    `https://www.awesomeapp.com/NotifyCustomerStateChange`

    Optionally, turn on **Configure per Environment** to set different URLs for SOD, Stage, and Production.

    ![Configure notifications per environment -screenshot][img2]

6. [!include[Has integration?](includes/has-integration.md)]

7. Click **Save Settings** or **OK**.

8. [Request to publish the new configuration.][3]
<!-- markdownlint-restore -->

> [!NOTE]
> You must set up a web service listening at the given URL and be prepared to [parse notifications][2].

## ERP sync, quote, and mirroring

For each endpoint you have configured SuperOffice to send data to, you can also subscribe to error emails.

To turn on/off error emails to the technical contact for an endpoint, update the advanced configuration of the application.

* [ERP sync][5]
* [Quote connector][6]
* [Database mirror][4]

To receive error emails at different or more than one email addresses, update the application settings:

1. On the app page, select **Settings** from the left menu or click the **Edit** button.

2. Scroll to the bottom and enter one or more addresses in the **Error reporting emails** field.

    ![Application settings, error reporting emails -screenshot][img3]

    The addresses must be separated with a semicolon ( ; ), no spaces.

3. Click **Save Settings**.

> [!NOTE]
> You can update the email addresses in the application settings at any time. Technical contact will receive any notification mail if this field is blank.

## Other errors

For other errors, such as when a customer reports a problem from the App Store, the technical contact will be notified if error reporting emails field is empty.

## Read more

* [How to change contact person][8]
* [About tenant status notifications][1]
* [Troubleshooting authorizing an application and working with tokens][7]

<!-- Referenced links -->
[1]: ../../apps/tenant-status/notifications.md
[2]: ../../apps/tenant-status/parse-notifications.md
[3]: request-to-publish.md
[4]: update-endpoints.md#database-mirroring
[5]: update-endpoints.md#erp-sync
[6]: update-endpoints.md#quote-connector
[7]: ../../api/authentication/online/troubleshooting/index.md
[8]: update-contact-person.md

<!-- Referenced images -->
[img1]: media/notifications.png
[img2]: media/endpoint-per-envir.png
[img3]: media/error-reporting-emails.png
