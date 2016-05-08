# Huffman-encoding-using-matlab
Huffman encoding using Matlab
clear all;

clc;

n=5; % no. of inputs

disp(&#39;Probabilities of messages :&#39;);

p=[0.4 0.2 0.1 0.2 0.1];disp(p);

s=1:n;

[dict,avglen]=huffmandict(s,p);

disp(&#39;Huffman Dicitionary :&#39;);disp(dict);

disp(&#39;Huffman bit length :&#39;);disp(avglen);

temp = dict;

for i=1:length(temp)

temp{i,2}=num2str(temp{i,2});

end

disp(temp);

sig=[1 3 4 2];

disp(&#39;String of message:&#39;);disp(sig);

disp(&#39;Huffman codes for given messages:&#39;);

sc=huffmanenco(sig,dict);disp(sc);

disp(&#39;Received bit string:&#39;);

mr=[1 0 0 1 1 0 1 0 0 0];

mo=huffmandeco(mr,dict);

disp(mo);

err=isequal(sig,mo);

if err==1

disp(&#39;Message recovered correctly&#39;);

else

disp(&#39;Error in decoding&#39;);

end
