---
title: Cómo crear un envío Port1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf49b16da34c5341059db34d6874b7099ab54df6
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015043"
---
# <a name="how-to-create-a-send-port"></a>Cómo crear un puerto de envío
Use el procedimiento siguiente para crear puertos de envío de BizTalk Server para JD Edwards EnterpriseOne.  
  
### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  Haga clic con el botón secundario en el nodo Puertos de envío.  
  
2.  Haga clic en **agregar puerto de envío**.  
  
3.  En el **crear nuevo puerto de envío** cuadro de diálogo, seleccione **puerto de petición-respuesta estático** desde el **especificar el tipo de puerto de envío** lista y haga clic en **Aceptar**.  
  
     El **propiedades de puerto de envío de petición-respuesta estático** abre la ventana.  
  
4.  Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToJDEEntOne`.  
  
5.  Haga clic en **transporte** en el panel izquierdo.  
  
6.  Haga clic en **tipo de transporte**y seleccione **JDEEntOne**.  
  
7.  Seleccione el **dirección (URI)** y haga clic en el botón de puntos suspensivos (...).  
  
     JD Edwards EnterpriseOne **propiedades de transporte** aparece el cuadro de diálogo.  
  
8.  Tipo de `myJDEEntOneSSO` para el **nombre lógico del sistema**.  
  
9. Seleccione **Sí** para **usar SSO**.  
  
10. En la lista desplegable, seleccione la aplicación afiliada al inicio de sesión único (SSO) que creó para representar el sistema JD Edwards EnterpriseOne.  
  
     Haga clic en **Aceptar** para confirmar la información que especificó.  
  
## <a name="see-also"></a>Vea también  
 [Creación de aplicaciones afiliadas](../core/creating-affiliate-applications4.md)   
 [Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)