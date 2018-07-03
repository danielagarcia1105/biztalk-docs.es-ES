---
title: Importación de certificados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96bdc2a681cf3632f6393a3fef05ec275f60f82f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006085"
---
# <a name="importing-certificates"></a>Importación de certificados
En esta sección se describe cómo importar certificados, incluidos where importarlos desde dónde almacenarla y qué herramientas para utilizar para importarlos.  
  
 Hay dos formas de importar los certificados. Puede usar la herramienta CertWizard o el complemento certificados para Microsoft Management Console (MMC).  
  
- CertWizard es un asistente paso a paso de línea de comandos que configura el uso del certificado según la configuración de modificadores. Esta herramienta está disponible en Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] carpeta del SDK.  
  
- Con el complemento de certificados en MMC, puede importar un certificado al almacén de certificados. Sin embargo, este proceso manual requiere que configure el uso del certificado por separado.  
  
  > [!IMPORTANT]
  >  Para importar o trabajar con certificados privados en MMC, el usuario que ha iniciado sesión debe tener la identidad del usuario de los Hosts de BizTalk. Si no, debe ejecutar el **runas** comando con el modificador de usuario y la cuenta de servicio de host para iniciar MMC certificados, por ejemplo, **runas /user:hostsvc mmc**. Al ejecutar este comando, asume la identidad de usuario de los Hosts de BizTalk (BizTalkServerApplication y BizTalkServerIsolatedHost).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Orígenes de certificados y almacenes](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [Importación de certificados mediante la utilidad CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [Importación de certificados mediante MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)