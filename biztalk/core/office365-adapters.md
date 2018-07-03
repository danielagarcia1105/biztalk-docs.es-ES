---
title: Usar el adaptador de correo electrónico de Office 365 Outlook | Microsoft Docs
description: Información general de enviar y recibir mensajes mediante los adaptadores de Office 365 Outlook en BizTalk Server, incluido el correo electrónico, calendario y contactos
ms.custom: ''
ms.date: 06/19/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 2002ab6859a71a930ef9166f9b3a5a072ba77948
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946235"
---
# <a name="office-365-outlook-adapters-in-biztalk"></a>Adaptadores de Outlook de Office 365 en BizTalk

## <a name="overview"></a>Información general
**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] característica Pack 3**, puede enviar y recibir mensajes entre las características de BizTalk Server y Office 365 Outlook. Los siguientes adaptadores se incluyen en la característica módulo 3:

- [Adaptador de correo electrónico de Outlook de Office 365](office365-mail-adapter.md)
- [Adaptador de calendario de Outlook de Office 365](office365-calendar-adapter.md)
- [Adaptador de contacto de Outlook de Office 365](office365-contact-adapter.md)

## <a name="prerequisites"></a>Requisitos previos

* Tiene un [cuenta de Office 365](https://outlook.office365.com)
* Instalar [Feature Pack 3 de](https://aka.ms/bts2016fp3) en el servidor BizTalk Server
* Usar una cuenta que sea miembro del grupo de administradores de SSO

## <a name="tms-overview"></a>Información general TMS

BizTalk Server TMS es un servicio que actualiza los tokens de OAuth de Office 365 usados por BizTalk. Actualizan estos tokens periódicamente, lo que garantiza que los tokens siempre sigue siendo válidos. Tiene una dependencia en el servicio Enterprise Single Sign On (SSO ENT) y debe instalarse en un equipo que hospeda el servidor secreto principal. 

## <a name="install-biztalk-server-tms"></a>Instalar a BizTalk Server TMS

1. Instalar [Feature Pack 3 de](https://aka.ms/bts2016fp3).
2. En `\Program Files (x86)\Microsoft BizTalk Server <your version>`, ejecute BizTalkTMS.msi.
3. Escriba el nombre de usuario y la contraseña de un usuario que sea miembro del grupo de administradores de SSO. 

![Programa de instalación de BizTalk Server TMS](../core/media/BizTalk-TMS.png)

## <a name="sign-in-to-office-365"></a>Inicie sesión en Office 365

Cuando creas un [puerto de envío](how-to-create-a-send-port2.md) o [ubicación de recepción](how-to-create-a-receive-location.md) en administración de BizTalk, puede **inicio de sesión...**  a su cuenta de Office 365:

  ![Inicio de sesión de Office 365](../core/media/office365-signin.png)

Escriba las credenciales de Office 365 y confirmar los permisos. Estas credenciales autorización BizTalk al que conectarse y acceder a la cuenta de Office 365. En el ejemplo siguiente, puede ver los permisos para el calendario de Outlook de Office 365:

  ![Permisos del calendario de Office 365](../core/media/office365-calendar-permissions.png)

## <a name="get-started"></a>Introducción
Después de instalar BizTalk Server TMS, está listo para crear los artefactos y empezar a usar los adaptadores:

- [Adaptador de correo electrónico de Outlook de Office 365](./office365-mail-adapter.md)
- [Adaptador de calendario de Outlook de Office 365](./office365-calendar-adapter.md)
- [Adaptador de contacto de Outlook de Office 365](./office365-contact-adapter.md)
