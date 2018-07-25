Scriptless-page-object

http://www.testautomationguru.com/selenium-webdriver-scriptless-page-object-design-pattern-part-1/

http://www.testautomationguru.com/selenium-webdriver-scriptless-page-object-design-pattern-part-2/

http://www.testautomationguru.com/selenium-webdriver-scriptless-page-object-design-pattern-part-3/

Run the below command in the chrome console which is responsible for creating the page object.

var pageObjectModel = function(root){
    $j(root).find('input, select, textarea').filter(':enabled:visible:not([readonly])').each(function(){
            let eleName = this.name;
            let key = this.tagName + "#" + (this.getAttribute('type') || '');
            var func = eleMap[key] || eleMap['INPUT#text'];
            func(this);
    });
    console.log(JSON.stringify(eles, null, 4));
}

