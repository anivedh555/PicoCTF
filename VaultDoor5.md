    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());         <========================= Password is url encoded
        String base64Encoded = base64Encode(urlEncoded.getBytes()); <========================= then it is base64 encoded
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTMxJTMxJTM3JTM3JTY2JTM3JTM4JTMz";
	System.out.println(expected);
        return base64Encoded.equals(expected);
    }
}


Let's follow the reverse procedure. Let's first print the expected variable, then base64 decode it and then later on lets use a url decoder.

expected = JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTMxJTMxJTM3JTM3JTY2JTM3JTM4JTMz

after base64 decoding, we get %63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%31%31%37%37%66%37%38%33

after url decoding this we get, c0nv3rt1ng_fr0m_ba5e_64_1177f783

There you go, that's your flag
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_1177f783}
