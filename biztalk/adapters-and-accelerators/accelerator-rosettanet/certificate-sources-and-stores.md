---
title: Orígenes y los almacenes de certificados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, certificate storage
- importing certificates
- certificates, certificate sources
- certificates, importing
ms.assetid: 3e98fb56-4368-46f3-9329-c44fed11f4fb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13272f66fca9faec099d8fe8f1b6fb69bb1e6660
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990341"
---
# <a name="certificate-sources-and-stores"></a>Orígenes de certificados y almacenes
Este tema describe dónde importar certificados y dónde almacenar los certificados.  
  
## <a name="certificate-sources"></a>Orígenes de certificados  
 Importar certificados desde los siguientes archivos:  
  
- Certificados privados de los archivos .pfx o. p12. Después de importar los certificados, almacene estos archivos de forma segura. Si importa los certificados privados mediante la utilidad CertWizard, puede establecer el **/Exportable** cambie a `False`, que es la configuración predeterminada, para que los certificados privados no se puede exportar desde la tienda en un archivo. Si establece la **/Exportable** cambie a `True`, puede exportar estos certificados a un archivo de certificados de Microsoft Management Console (MMC).  
  
- Certificados públicos de los archivos .cer o .der. Asociados de envían sus certificados para usted en estos archivos.  
  
- Certificados raíz de los archivos .cer o .der. Entidades de certificación enviar sus certificados raíz para usted en estos archivos.  
  
## <a name="certificate-storage"></a>Almacenamiento de certificados  
 Importar certificados a uno de los dos almacenes de certificados en el equipo local. Almacenar certificados públicos en el **certificados (equipo Local)** almacenar. Puede abrir los nodos de este almacén abriendo el **certificados (equipo Local)** nodo en Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console. Puede tener acceso a la **certificados (equipo Local)** almacenar si tiene permisos administrativos en el equipo. Store certificados públicos en las siguientes carpetas:  
  
- Certificados públicos en la carpeta Personal de inicio la **certificados (equipo Local)** almacenar  
  
- De asociados certificados públicos en la carpeta de otras personas de la **certificados (equipo Local)** almacenar  
  
- Certificados de entidades de certificación en la carpeta de la entidad de certificación raíz de confianza de la **certificados (equipo Local)** almacenar  
  
  Almacenar certificados privados en el **certificados - usuario actual** almacenar. Puede abrir los nodos de este almacén, abra la consola de administración utilizando la **runas** comando con el usuario de cuenta de servicio de host. Para obtener más información, consulte [importar certificados](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md).  
  
## <a name="see-also"></a>Vea también  
 [Importación de certificados mediante la utilidad CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)   
 [Importación de certificados mediante MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)   
 [Importación de certificados &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)