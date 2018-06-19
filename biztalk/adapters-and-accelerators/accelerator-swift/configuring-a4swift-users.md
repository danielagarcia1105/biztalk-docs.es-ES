---
title: Configuración de A4SWIFT usuarios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, user accounts
- creating, user accounts
- user accounts, creating
ms.assetid: 45dcbece-ec8d-410a-8320-79bfbc4c779d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79c3b63cd77bb34545f4c4093796310aa7720563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209380"
---
# <a name="configuring-a4swift-users"></a>Configuración de los usuarios de A4SWIFT
Durante la instalación de [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], el programa de configuración de A4SWIFT crea perfiles de socios comerciales de forma predeterminada y contratos y registra el servidor BizTalk Server. A4SWIFT también crea bibliotecas de documentos usadas por el componente de reparación de mensajes y nuevo envío.  
  
 A4SWIFT crea las siguientes carpetas de documentos durante la instalación:  
  
-   Biblioteca de documentos de bandeja de salida  
  
-   Biblioteca de documentos de plantillas  
  
-   Biblioteca de documentos sin analizar  
  
-   Nueva biblioteca de documentos de mensajes de SWIFT MT  
  
-   Nueva biblioteca de documentos de mensajes de SWIFT MX  
  
 Para cada departamento creado, el Administrador de A4SWIFT debe establecer manualmente los grupos de sitio para los departamentos correspondientes y funciones definidas de A4SWIFT. Cada departamento/rol tiene una bandeja de entrada que se crea automáticamente el Client(PWC) Web de perfil.  
  
 Después de completa el programa de configuración del programa de instalación de A4SWIFT, el Administrador de A4SWIFT configura los flujos de trabajo para cada departamento de la organización. Durante la configuración de la reparación de mensajes y nuevo envío, a través del cliente Web de perfil, se crean las bandejas de entrada correspondientes para cada combinación de departamento o el rol. Por ejemplo, durante la configuración de PWC un administrador de A4SWIFT crea un departamento con el nombre de pagos y, a continuación, asigna los roles de creadores, talleres de reparación y aprobadores a un departamento denominado pagos. Las bibliotecas de documentos en el sitio MRSR se crean con los nombres de la Bandeja de entrada, como se muestra en los ejemplos en la tabla siguiente:  
  
|Nombre de departamento|Nombre de rol|Nombre de la Bandeja de entrada|  
|---------------------|---------------|----------------|  
|Pagos|Creadores de|Payments_Creator|  
|Pagos|Talleres de reparación|Payments_Repairers|  
|Pagos|Aprobadores|Payments_Approvers|