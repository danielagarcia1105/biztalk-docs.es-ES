---
title: Configurar un informe de estado de AS2 y EDI | Microsoft Docs
description: Creación de EDI o expresión de consulta de informes de estado de AS2 y seleccionar los datos que desea mostrar en el informe para el servidor BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6490864d-f1e6-4932-aefb-c332a595aad7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4981067305a6b1de57c393cea7d49323933a0ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972805"
---
# <a name="configure-an-edi-and-as2-status-report"></a>Configurar un informe de estado de AS2 y EDI
Una vez que ha habilitado EDI o informes de estado de AS2, muestre el informe de estado que desee desde la **informes de estado de EDI** o **informes de estado de EDIINT** sección de la **concentrador de grupo** pestaña de la **información general del grupo** página en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Al mostrar un informe de estado, verá un conjunto de datos predeterminado. Puede configurar los siguientes aspectos de los informes de estado:  
  
- La expresión de la consulta que se ejecuta para determinar el intervalo de datos que notifica el estado, por ejemplo, el rango de fechas, la dirección de los datos (recibidos o enviados) o el valor del estado (Aceptado, Rechazado, Todo, etc.)  
  
- El tipo de datos que aparece en el panel de informe de estado, como determina las columnas de datos del informe.  
  
  > [!NOTE]
  >  Siempre que el informe de estado esté habilitado, todos los estados se guardarán en su ubicación. Mediante la personalización de la expresión de consulta o columnas de estado, se definen los datos guardados que se visualizan.  
  
  Existen cinco informes de estado diferentes EDI y AS2 (consulte [tipos de informes de EDI y AS2 estado](../core/types-of-edi-and-as2-status-reports.md)). El modo de configuración de los informes es el mismo, aunque los datos de los informes sean distinto.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="configure-the-status-report-query-expression"></a>Configurar la expresión de consulta del informe de estado  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **grupo de BizTalk** nodo para ver el **información general del grupo** panel.  
  
2. En la parte inferior de la **concentrador de grupo** pestaña en el **información general del grupo** panel, haga clic en el informe de estado que desee configurar, por ejemplo, **intercambio EDI y estado de confirmación correlacionado**.  
  
3. En el **expresión de consulta** área del panel de informe de estado, compruebe que todos los criterios de filtro que desea definir la consulta están presentes. Si no aparece, haga clic en la flecha hacia abajo en la fila vacía de la **nombre de campo** columna en la parte inferior de la expresión de consulta y seleccione los criterios que desea agregar a la expresión de consulta de filtro. Puede eliminar una fila de criterios de filtro, seleccione la fila y haciendo clic en el **eliminar** botón en el teclado.  
  
4. Compruebe que los valores de las expresiones de filtro son los deseados. Si no aparece, haga clic en la flecha abajo de la **operador** columna para seleccionar una operación de consulta y escriba el valor adecuado en el **valor** columna.  
  
   > [!NOTE]
   >  Los operadores y valores disponibles para los criterios de filtro en las expresiones de consulta se describen en [tipos de informes de EDI y AS2 estado](../core/types-of-edi-and-as2-status-reports.md) y **interfaz de usuario de informes de estado de EDI / AS2** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
5. Para ejecutar la consulta que muestra el informe de estado según los criterios de filtro, haga clic en **Ejecutar consulta**.  
  
6. Para guardar una expresión de consulta como archivo .btq, haga clic en **Guardar como**, especifique la carpeta y escriba un nombre de archivo y, a continuación, haga clic en **guardar**.  
  
7. Para abrir un archivo guardado como .btq, haga clic en **Abrir consulta**.  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a>Configurar el tipo de datos que se muestran en el panel de informe de estado  
  
1.  Haga clic en el área de resultados del panel de informe de estado y, a continuación, haga clic en **agregar o quitar columnas**.  
  
2.  Para agregar una categoría de estado a la lista de columnas mostradas, haga clic en una columna en la **columnas disponibles** lista y, a continuación, haga clic en **agregar**.  
  
3.  Para quitar una categoría de estado de la lista de columnas mostradas, haga clic en una columna en la **columnas mostradas** lista y, a continuación, haga clic en **quitar**.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de soluciones EDI y AS2](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI y AS2 de informes de estado](../core/edi-and-as2-status-reporting.md)   
 [Habilitar informes de estado de AS2 y EDI](../core/enabling-edi-and-as2-status-reports.md)   
 [Mostrar un informe de estado de EDI o AS2](../core/displaying-an-edi-or-as2-status-report.md)