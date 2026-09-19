class Solution {
public:
    ListNode* mergeKLists(vector<ListNode*>& lists) {
        struct Compare
        {
            bool operator() (ListNode* a, ListNode* b)
            {
                return a->val > b->val;
            }
        };
        priority_queue<ListNode*, vector<ListNode*>, Compare> pq;
        ListNode* result = nullptr;
        ListNode* last = nullptr;
        for(int i = 0; i < lists.size(); i++)
        {
            if (lists[i] != nullptr)
            {
                pq.push(lists[i]);
            }
        }
        while (!pq.empty())
        {
            ListNode* node = pq.top();
            pq.pop();
            ListNode* nextNode = node->next;
            if (result == nullptr)
            {
                result = node;
                last = node;
            }
            else
            {
                last->next = node;
                last = node;
            }
            if(nextNode != nullptr)
            {
                pq.push(nextNode);
            }
        }
        return result;
    }
};
