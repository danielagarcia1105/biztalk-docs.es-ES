---
title: Importación de certificados | Documentos de Microsoft
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
ms.openlocfilehash: c78773d6eb1fc7e51ca80afadfd282d54def80b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209980"
---
# <a name="importing-certificates"></a>Importación de certificados
Esta sección describe cómo importar certificados, como dónde desea importarlos desde, dónde desea almacenarlos y qué herramientas para utilizar para importarlos.  
  
 Hay dos maneras de importar los certificados. Puede usar la herramienta CertWizard o el complemento de certificados para [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).  
  
-   CertWizard es un asistente paso a paso de línea de comandos que configura el uso del certificado según la configuración de los conmutadores. Esta herramienta está disponible en la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] carpeta del SDK.  
  
-   Con el complemento de certificados en MMC, puede importar un certificado en el almacén de certificados. Sin embargo, este proceso manual requiere que configure el uso del certificado por separado.  
  
    > [!IMPORTANT]
    >  Para importar o trabajar con certificados privada en MMC, el usuario que ha iniciado sesión debe tener la identidad del usuario de los Hosts de BizTalk. Si no es así, debe ejecutar el **runas** comando con el modificador de usuario y la cuenta de servicio de host para iniciar la consola de MMC de certificados, por ejemplo, **runas /user:hostsvc mmc**. Al ejecutar este comando, asume la identidad de usuario de los Hosts de BizTalk (BizTalkServerApplication y BizTalkServerIsolatedHost).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Orígenes de certificados y almacenes](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [Importación de certificados mediante la utilidad CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [Importación de certificados mediante MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)