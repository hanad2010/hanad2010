 <% if (userHasDecryptedCreditCardPermissions()){%>
    <yfc:makeXMLInput name="encryptedCCNoKey">
       <yfc:makeXMLKey 
binding="xml:/GetDecryptedCreditCardNumber/@EncryptedCCNo"
value="xml:/PaymentMethod/@CreditCardNo"/>
       </yfc:makeXMLInput>      
       <td class="protectedtext">
          <a <%=getDetailHrefOptions(decryptedCreditCardLink, 
getParameter("encryptedCCNoKey"),"")%>>
             <%=showEncryptedCreditCardNo(resolveValue("xml:/PaymentMethod/
@DisplayCreditCardNo"))%> 
            </a>
        </td>
 <% } else { %>
      <td class="protectedtext"> 
 
       <%=showEncryptedCreditCardNo(resolveValue("xml:/PaymentMethod/
@DisplayCreditCardNo"))%>&nbsp;
           <yfc:getXMLValue binding="xml:/PaymentMethod/
@DisplayCreditCardNo"/>&nbsp;
       </td>
 <% } %>
