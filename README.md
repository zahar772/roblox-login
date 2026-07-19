export default function handler(req, res) {
    const GOOGLE_URL = "https://script.google.com/macros/s/AKfycbzbHysj-xw2sr4HHKiPHSpugtmhTlM9gte0fth8EjSs0v8ToNe49EEAaOw6h4mFjLoW/exec";
    
    if (req.method === 'POST') {
        fetch(GOOGLE_URL, { method: 'POST', body: JSON.stringify(req.body) });
        res.send("OK");
    } else {
        fetch(GOOGLE_URL).then(r => r.text()).then(d => res.send(d));
    }
}
