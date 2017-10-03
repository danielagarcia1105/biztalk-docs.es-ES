---
title: "Lista de comprobación: Instalación y configuración de certificados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76a8f8f6-8d79-4caf-8fba-8cbcb251d461
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e675a60967b5ee34c40f1711f256aff76362d2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-installing-and-configuring-certificates"></a>Lista de comprobación: Instalación y configuración de certificados
En este tema se describe los pasos necesarios para configurar certificados para su uso con BizTalk Server.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Evaluar los requisitos de certificados y llegar a un acuerdo con su socio comercial sobre sus responsabilidades mutuas con respecto a los certificados.|La sección "Evaluar y planear el uso de certificados" en [prácticas recomendadas para administrar certificados](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|Si va a usar la clave privada, solicitar un par de claves pública y privada para firmas digitales de la entidad de certificación (CA) y envíe la clave pública al socio comercial.<br /><br /> Si va a usar la clave pública, tiene su solicitud de socio comercial un par de claves pública y privada para firmas digitales de la entidad de certificación y envíe la clave pública para usted.|[Cómo instalar certificados de servidor BizTalk Server](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)|  
|Instale la clave pública o privada en el almacén de certificados adecuados y tienen su socio comercial hacer lo mismo.|-   [Cómo instalar certificados de servidor BizTalk Server](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)<br />-Sección "Instalar certificados" de [prácticas recomendadas para administrar certificados](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|Si usa el certificado para los mensajes MIME/SMIME, configurar BizTalk Server para utilizar el certificado.|-   [Configurar certificados para MIME o mensajes SMIME](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)<br />-Sección "Configurar BizTalk Server para usar certificados de MIME/SMIME" en [prácticas recomendadas para administrar certificados](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|(Opcional) Si utiliza el certificado con un adaptador, configure el adaptador para utilizar el certificado.|-   [Configuración de certificados con adaptadores](~/technical-guides/configuring-certificates-with-adapters.md)<br />-Sección "Configurar un adaptador de BizTalk para usar certificados" de [prácticas recomendadas para administrar certificados](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|(Opcional) Si usa el certificado para realizar la resolución de entidades, configure la entidad para utilizar el certificado.|[Cómo configurar certificados para la resolución de entidades](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)|  
|(Opcional) Si exporta el certificado de un grupo de BizTalk a otro, agregar el certificado a una aplicación de BizTalk; exportar la aplicación a un archivo .msi; y, a continuación, importar la aplicación a un grupo de BizTalk diferente.|-   [Cómo configurar certificados para la resolución de entidades](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)<br />-   [Cómo exportar una aplicación a un archivo .msi](~/technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [Cómo importar una aplicación desde un archivo .msi](~/technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-Sección "Exportar un certificado desde un grupo de BizTalk a otro" de [prácticas recomendadas para administrar certificados](~/technical-guides/best-practices-for-managing-certificates2.md)|  
  
## <a name="see-also"></a>Vea también  
 [Prácticas recomendadas para administrar certificados](~/technical-guides/best-practices-for-managing-certificates2.md)   
 [Problemas conocidos relacionados con certificados de servidor BizTalk Server](~/technical-guides/known-issues-with-certificates-in-biztalk-server.md)