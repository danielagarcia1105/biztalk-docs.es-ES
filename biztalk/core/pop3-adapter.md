---
title: POP3 Adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, about POP3 adapters
- authenticating, POP3 adapters
- POP3 adapters
- POP3 adapters, receive adapters
- POP3 adapters, authenticating
- receive adapters, POP3 adapters
ms.assetid: 008f7fa7-60c3-4ea3-b90d-821e4029a04c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34a5f6a73f30ba831256ce1699b9a6a77b75c102
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982797"
---
# <a name="pop3-adapter"></a>Adaptador de POP3
El adaptador de Protocolo de oficina de correos v. 3 (POP3) se utiliza para recuperar datos de un servidor que aloja buzones POP3 a un servidor en el que se ejecuta Microsoft BizTalk Server mediante el protocolo POP3.  
  
 El adaptador de POP3 se compone de un solo adaptador: un adaptador de recepción. El adaptador de recepción controla las ubicaciones de recepción que utilizan el adaptador de POP3.  
  
 En este tema se analiza el flujo de trabajo del adaptador de recepción POP3.  
  
 **POP3 Adaptador de recepción**  
  
 El adaptador de recepción POP3 recupera el correo electrónico de un buzón definido de un servidor POP3 especificado. De forma predeterminada, el adaptador de recepción POP3 aplica el procesamiento de MIME a los mensajes de correo electrónico que descarga y los envía a BizTalk Server como mensajes de varias partes de BizTalk. El adaptador de recepción POP3 puede recibir mensajes de correo electrónico y procesarlos en los siguientes formatos:  
  
- Texto sin formato  
  
- Con codificación MIME  
  
- Con cifrado MIME  
  
- Con firma y con codificación MIME  
  
- Con firma y con cifrado MIME  
  
  **Soporte técnico de procesamiento por lotes para el adaptador de recepción POP3**  
  
  El adaptador de recepción POP3 no admite el procesamiento por lotes.  
  
  **Autenticación con servidor POP3**  
  
  Se admiten los siguientes métodos de autenticación para su uso con el adaptador de POP3:  
  
- **Básico.** El servidor POP3 utiliza credenciales proporcionadas por el usuario para la autenticación.  Estas credenciales se envían en texto no cifrado.  
  
- **Implícito (APOP).** El servidor POP3 utiliza una cadena implícita para la autenticación.  
  
- **Autenticación de contraseña segura (SPA).** El servidor POP3 utiliza credenciales del proceso actual para la autenticación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Qué es el adaptador de POP3?](../core/what-is-the-pop3-adapter.md)  
  
-   [Configuración del adaptador de POP3](../core/configuring-the-pop3-adapter.md)  
  
-   [Tutorial: Creación de una aplicación de BizTalk que usa el adaptador de POP3](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [Procesamiento de mensajes de varias partes con el adaptador de POP3](../core/processing-multi-part-messages-with-the-pop3-adapter.md)