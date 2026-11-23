---
title: "किसी कलाकार का सुझाव दें"
slug: suggest-an-artist
---

मुझे यीशु का अनुसरण करने वाले संगीतकारों और कलाकारों के बारे में सुनना बहुत अच्छा लगता है। अगर आप किसी ऐसे व्यक्ति को जानते हैं जिसके बारे में मैं लिखूँ, जिसका इंटरव्यू लूँ, या जिस पर रिएक्शन वीडियो बनाऊँ, तो यहाँ बताइए।

बस एक नाम और एक लिंक काफ़ी है — और कुछ शब्दों में यह भी कि वह क्यों। जो भी आता है, मैं सब पढ़ता हूँ। बहुत-बहुत धन्यवाद।

क्या कोई ऐसा है जिसे आप जानते हैं? उसकी तस्वीर पर टैप करें, फ़ॉर्म अपने आप भर जाएगा — फिर कुछ शब्दों में बताइए कि वह क्यों, और भेज दीजिए।

<div class="suggest-carousel" role="list" aria-label="जिन संगीतकारों और कलाकारों का आप सुझाव दे सकते हैं">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="{{ artist.name }} का सुझाव दें">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">या नीचे किसी नए व्यक्ति का सुझाव दें — जिसे भी आपको लगता है कि मुझे जानना चाहिए।</p>

यह साइट 18 साल से कम उम्र के लोगों के लिए नहीं है।

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">कलाकार का नाम</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="मुझे किसे देखना चाहिए?" required>

  <label for="suggest-link">सोशल मीडिया प्रोफ़ाइल लिंक</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>मैं उनके साथ क्या करूँ?</legend>
    <label><input type="checkbox" name="kind" value="write"> उनके बारे में लिखें</label>
    <label><input type="checkbox" name="kind" value="interview"> इंटरव्यू लें</label>
    <label><input type="checkbox" name="kind" value="reaction"> उन पर रिएक्शन वीडियो बनाएँ</label>
  </fieldset>

  <label for="suggest-why">वह क्यों?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="कुछ शब्द ही काफ़ी हैं…"></textarea>

  <label for="suggest-name">आपका नाम <span class="optional">(वैकल्पिक)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="ताकि मैं धन्यवाद कह सकूँ">

  <label for="suggest-from-link">आपकी सोशल मीडिया प्रोफ़ाइल लिंक <span class="optional">(वैकल्पिक)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">सुझाव भेजें</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
