---
title: Utilidad BatchTerminator | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 771241fa-7df5-4882-8430-c2f36200cc9d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 080f82993fc3c8c62b3764d496f03589bd06364e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967354"
---
# <a name="batchterminator-utility"></a>BatchTerminator (utilidad)
La utilidad BatchTerminator permite determinar todas las orquestaciones de procesamiento por lotes activas que se van a usar para procesar intercambios EDI. Esta utilidad puede ser de ayuda si ejecuta una gran cantidad de instancias de orquestaciones de procesamiento por lotes y es necesario finalizar todos los lotes para realizar el mantenimiento en el sistema de de BizTalk Server.  
  
 La utilidad BatchTerminator se encuentra en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator. Al ejecutar la utilidad para finalizar las instancias de orquestación de procesamiento por lotes, la utilidad registrará los resultados en el archivo batchterminator.log de la \< *unidad*\>: \Documents and Settings\\ < *nombre de usuario*\>\Application carpeta de datos.  
  
> [!NOTE]
>  La utilidad BatchTerminator solo se admite en sistemas de 32 bits.  BatchTerminator usa componentes del espacio de nombres de Microsoft.BizTalk.ExplorerOM, que solo se admite si se usa desde un proceso de 32 bits.  
  
 **Reiniciar las instancias de orquestación finalizadas**  
  
 Una vez finalizado el grupo de orquestaciones de procesamiento por lotes, puede realizar un reinicio masivo de dichas instancias de orquestaciones. Puede hacerlo con el modificador /Activate, el nombre y la ruta de un archivo que indica los lotes que se han detenido. Si ejecuta la utilidad para finalizar un grupo de instancias de orquestaciones, la utilidad creará este archivo de procesamientos por lotes detenido. El archivo de procesamiento por lotes detenido es batchSettings -\<GUID\>.xml en el \< *unidad*\>: \Documents and Settings\\<*nombre de usuario*  \>\Application carpeta de datos. La ruta y el nombre del archivo de procesamiento por lotes detenido también se guardan en el archivo de registro. Si la utilidad se ejecuta con el modificador /activate, valida el archivo de entrada con un esquema.  
  
 **Sintaxis**  
  
 Ejecute la utilidad BatchTerminator en una ventana de línea de comandos con la siguiente sintaxis:  
  
```  
BatchTerminator /<switch>  
```  
  
 Puede ejecutar la utilidad BatchTerminator con los siguientes modificadores. Si no se proporciona ningún modificador, se usa la opción /terminate. Como se indica a continuación, puede especificar el nombre completo del modificador, por ejemplo, /terminate o la forma abreviada, en este caso, /t.  
  
|||  
|-|-|  
|Switch|Función|  
|/?|Muestra la ayuda.|  
|/ terminar - registro:\<*archivo de registro*\><br /><br /> o/t.-registro:\<*archivo de registro*\>|Envía mensajes de control finalizados a todas las instancias de orquestaciones de procesamiento por lotes X12 o EDIFACT activas. Muestra los resultados de la operación, incluida una lista de todas las instancias de orquestaciones de procesamiento por lotes activas que han finalizado, el número de orquestaciones de procesamiento por lotes activas que ha encontrado y el número de mensaje de control finalizados que ha enviado. Registra los resultados en el archivo batchterminator.log de la \< *unidad*\>: \Documents and Settings\\<*nombre de usuario*\>\ Carpeta de datos de aplicación.<br /><br /> -Log opcional: parámetro le permite especificar el nombre del archivo de registro o la ruta de acceso de la carpeta que desea que se guarden en el archivo de registro. Un ejemplo de uso del parámetro para especificar la ruta de acceso y nombre de archivo es el siguiente: `BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`. Un ejemplo de uso del parámetro para especificar el nombre de archivo sólo es el siguiente: `BatchTerminator.exe /terminate -log:log.txt`. Si la ruta de acceso especificada no es válida, la utilidad usará la ruta de acceso predeterminada: \< *unidad*\>: \Documents and Settings\\<*nombre de usuario* \>\Application datos. -Log: parámetro que puede utilizarse con o sin el modificador / terminate.|  
|/print<br /><br /> o /p|Muestra una lista de las instancias de orquestación de procesamiento por lotes activas actuales sin enviar los mensajes de control finalizados que se van a enviar.|  
|Activar o:\<*ruta de acceso*\>\\<br />batchSettings -\<*GUID*\>.xml-registro:\<*archivo de registro*\><br /><br /> o bien, / a:\<*ruta de acceso*\>\\<br />batchSettings -\<*GUID*\>.xml-registro:\<*archivo de registro*\>|Vuelve a activar las instancias de orquestación finalizadas anteriormente que se muestran en la batchSettings -\<GUID\>archivo .xml. La utilidad validará el archivo de entrada con un esquema integrado en el código. Si el archivo de entrada no coincide con el esquema, se imprimirá un mensaje de error en la pantalla y saldrá del programa.<br /><br /> Esta operación escribe información acerca de la acción de reinicio en el archivo de registro si incluye - log: cambiar.|  
  
 **Formato del archivo de activación por lotes**  
  
 Para reactivar previamente terminado instancias de orquestación de procesamiento por lotes mediante el modificador / activate, debe proporcionar un archivo de activación por lotes (batchSettings -\<GUID\>.xml). Este archivo debe tener el siguiente formato:  
  
```  
<?xml version="1.0"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" elementFormDefault="qualified" id="BatchInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="BatchTerminator">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="Batch">  
          <xs:complexType>  
            <xs:attribute name="PartyName" type="xs:string" />  
            <xs:attribute name="PartyID" type="xs:int" use="required" />  
            <xs:attribute name=”BatchName” type=”xs:string” />  
            <xs:attribute name=”BatchID” type=”xs:int” use=”required” />  
            <xs:attribute name="EdiMessageType" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  
  
-   Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-run-the-batchterminator-utility"></a>Para ejecutar la utilidad BatchTerminator  
  
1.  En el Explorador de Windows, desplácese a la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator.  
  
2.  ENTRAR **BatchTerminator**, incluidos los modificadores que desee y, a continuación, haga clic en **ENTRAR**.  
  
3.  En el Explorador de Windows, desplácese a \< *unidad*\>: \Documents and Settings\\<*nombre de usuario*\>\Application carpeta de datos, y Abra el archivo batchterminator.log para ver un registro de los resultados.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades del SDK](../core/utilities-in-the-sdk.md)