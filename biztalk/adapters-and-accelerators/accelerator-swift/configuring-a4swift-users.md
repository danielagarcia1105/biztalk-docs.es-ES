---
title: Configuración de usuarios de A4SWIFT | Microsoft Docs
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
ms.openlocfilehash: b75a3e95c836f8a577543b43319e6abe49a96c42
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005261"
---
# <a name="configuring-a4swift-users"></a>Configurar usuarios de A4SWIFT
Durante la instalación de [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], el programa de configuración de A4SWIFT crea perfiles de socios comerciales de forma predeterminada y los acuerdos y registra el servidor BizTalk Server. A4SWIFT también crea las bibliotecas de documentos que se utiliza el componente de reparación de mensajes y nuevo envío.  
  
 A4SWIFT crea las siguientes carpetas de documento durante la instalación:  
  
- Biblioteca de documentos de bandeja de salida  
  
- Biblioteca de documentos de plantillas  
  
- Biblioteca de documentos sin analizar  
  
- Nueva biblioteca de documentos de mensaje MT de SWIFT  
  
- Nueva biblioteca de documentos de mensajes MX de SWIFT  
  
  Para cada departamento creado, el Administrador de A4SWIFT debe configurar manualmente los grupos de sitio para los departamentos correspondientes y funciones definidas de A4SWIFT. Cada departamento o el rol tiene una bandeja de entrada creado automáticamente por el Client(PWC) Web de perfil.  
  
  Después de completa el programa de configuración del programa de instalación de A4SWIFT, el Administrador de A4SWIFT configura flujos de trabajo para cada departamento de la organización. Durante la configuración de la reparación de mensajes y nuevo envío, mediante el cliente Web de perfil, se crean las bandejas de entrada correspondientes para cada combinación de departamento o rol. Por ejemplo, durante la configuración de PWC A4SWIFT administrador crea un departamento con el nombre de los pagos y, a continuación, asigna las funciones de creadores, talleres y aprobadores para un departamento de pagos. Las bibliotecas de documentos en el sitio MRSR se crean con los nombres de la Bandeja de entrada, como se muestra en los ejemplos en la tabla siguiente:  
  
|Nombre de departamento|Nombre de rol|Nombre de la Bandeja de entrada|  
|---------------------|---------------|----------------|  
|Pagos|Creadores|Payments_Creator|  
|Pagos|Talleres de reparación|Payments_Repairers|  
|Pagos|Aprobadores|Payments_Approvers|