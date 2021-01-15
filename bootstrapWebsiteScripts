if(typeof decodeHtml != 'function'){
    function decodeHtml(html) {
        var txt = document.createElement("textarea");
        txt.innerHTML = html;
        return txt.value;
    }
}
$('.website-search').submit(function(event){
    var allInputs = $(this).find('input:not([type=hidden])');
    var allSelects = $(this).find('select');
    var inputsToClean = $.merge(allInputs, allSelects)
    var input, i;

    for(i = 0; input = inputsToClean[i]; i++) {
        if(input.getAttribute('name') && !input.value) {
            input.setAttribute('name', '');
        }
    }
})
$(document).on('paste', 'input[type="email"]', function(e) {
    e.preventDefault();
    var withoutSpaces = e.originalEvent.clipboardData.getData('Text');
    withoutSpaces = withoutSpaces.replace(/\s+/g, '');
    $(this).val(withoutSpaces);
});

// Script to trigger form validation when content is pasted in inputs
$(document).on("paste", ".form-control", function(e) {
    $(".fv-form").formValidation("revalidateField", $(this).attr("data-fv-field"));
    if($(this).attr('name') == 'email'){
        if($('[name="email_confirm"]').val() != ''){
            $(".fv-form").formValidation("revalidateField", $('[name="email_confirm"]').attr("data-fv-field"));
        }
    }
});

function nl2br (str, is_xhtml) {
    var breakTag = (is_xhtml || typeof is_xhtml === 'undefined') ? '<br />' : '<br>';
    return (str + '').replace(/([^>\r\n]?)(\r\n|\n\r|\r|\n)/g, '$1'+ breakTag +'$2');
}
if(typeof $.fancybox == 'function') {
    $('.reviews-images-fancybox').fancybox({
        buttons: [
            "close"
        ],
        loop: true
    });
}
